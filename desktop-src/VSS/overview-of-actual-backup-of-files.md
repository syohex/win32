---
Description: VSS enables a requester to access the shadow copy of volumes containing data for backup and to copy data to backup media.
ms.assetid: 187f26f2-f191-4703-9bde-3357f1ceef0c
title: Overview of Actual Backup Of Files
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# Overview of Actual Backup Of Files

VSS enables a requester to access the shadow copy of volumes containing data for backup and to copy data to backup media. Writers generally proceed with normal operation during this process. For more information, see [Overview of Processing a Backup Under VSS](overview-of-processing-a-backup-under-vss.md).

The following table shows the sequence of actions and events that are required for files to be backed up.



<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Requester action</th>
<th>Event</th>
<th>Writer action</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Access files on the shadow-copied volume (see [<strong>IVssBackupComponents::GetSnapshotProperties</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-getsnapshotproperties?branch=master), [<strong>VSS_SNAPSHOT_PROP</strong>](/windows/win32/Vss/ns-vss-_vss_snapshot_prop?branch=master))</td>
<td>None</td>
<td>None</td>
</tr>
<tr class="even">
<td>Generate the list of files to back up, and copy file data to backup media.</td>
<td>None</td>
<td>None</td>
</tr>
<tr class="odd">
<td>Indicate the success or failure of the backup with [<strong>IVssBackupComponents::SetBackupSucceeded</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-setbackupsucceeded?branch=master).</td>
<td>None</td>
<td>None</td>
</tr>
<tr class="even">
<td>The requester indicates that the backup has completed by calling [<strong>IVssBackupComponents::BackupComplete</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-backupcomplete?branch=master).</td>
<td>[<em>BackupComplete</em>](vssgloss-b.md#base-vssgloss-backupcomplete-event)</td>
<td>Perform any post-backup cleanup (see [<strong>CVssWriter::OnBackupComplete</strong>](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onbackupcomplete?branch=master), [<strong>IVssWriterComponents</strong>](/windows/win32/VsWriter/nl-vswriter-ivsswritercomponents?branch=master), [<strong>IVssComponent</strong>](/windows/win32/VsWriter/nl-vswriter-ivsscomponent?branch=master)).</td>
</tr>
<tr class="odd">
<td>The requester waits for all writers to acknowledge receipt of the [<strong>IVssBackupComponents::BackupComplete</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-backupcomplete?branch=master) event using [<strong>IVssAsync</strong>](/windows/win32/Vss/nn-vss-ivssasync?branch=master). It should also verify writer status (see [<strong>IVssBackupComponents::GatherWriterStatus</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-gatherwriterstatus?branch=master), [<strong>IVssBackupComponents::GetWriterStatus</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-getwriterstatus?branch=master)). The requester must call <strong>GatherWriterStatus</strong> at this time to cause the writer session to be set to a completed state.
<blockquote>
[!Note]<br />
This is only necessary on Windows Server 2008 with Service Pack 2 (SP2) and earlier.
</blockquote>
<br/></td>
<td>None</td>
<td>None</td>
</tr>
<tr class="even">
<td>Save the Backup Components Document and each Writer Metadata Document to XML documents, which can be written to the backup media (see [<strong>IVssBackupComponents::SaveAsXML</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-saveasxml?branch=master) and [<strong>IVssExamineWriterMetadata::SaveAsXML</strong>](/windows/win32/VsBackup/nf-vsbackup-ivssexaminewritermetadata-saveasxml?branch=master)).</td>
<td>None</td>
<td>None</td>
</tr>
</tbody>
</table>



 

## Writer Actions during Backup of Files

After the shadow copy has been completed, all I/O operations on the system that is being backed up should be able to resume without disrupting the integrity of the backup. This is one of the prime motivations for having the shadow copy functionality.

Therefore, as in the discovery phase (see [Overview of the Backup Discovery Phase](overview-of-the-backup-discovery-phase.md)), there are few demands placed on the writers while files are actually being backed up.

After a backup has completed, and a requester has generated a [*BackupComplete*](vssgloss-b.md#base-vssgloss-backupcomplete-event) event, VSS will call each writer's [**CVssWriter::OnBackupComplete**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onbackupcomplete?branch=master) method, a virtual method that by default simply returns **TRUE**. However, writers can override the default implementation and take such actions as removing remaining temporary files, or use the [**IVssWriterComponents**](/windows/win32/VsWriter/nl-vswriter-ivsswritercomponents?branch=master) interface it is called with to check the state of the backup of each of its [*included explicitly*](vssgloss-e.md#base-vssgloss-explicit-component-inclusion) components (and any [*component set*](vssgloss-c.md#base-vssgloss-component-set) they might define) by retrieving the corresponding [**IVssComponent**](/windows/win32/VsWriter/nl-vswriter-ivsscomponent?branch=master) object. The writer can then determine, and act on, the success or failure of the backup by calling [**IVssComponent:GetBackupSucceeded**](/windows/win32/VsWriter/nf-vswriter-ivsscomponent-getbackupsucceeded?branch=master). The value returned by **IVssComponent:GetBackupSucceeded** will be **TRUE** only if all explicitly included files in the component and all [*implicitly included*](vssgloss-i.md#base-vssgloss-implicit-component-inclusion) of any of its [*subcomponents*](vssgloss-s.md#base-vssgloss-subcomponent) have been successfully backed up.

When the call to [**CVssWriter::OnBackupComplete**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onbackupcomplete?branch=master) has completed, the requester should call [**IVssBackupComponents::GatherWriterStatus**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-gatherwriterstatus?branch=master) and [**IVssBackupComponents::GetWriterStatus**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-getwriterstatus?branch=master) (for each writer) one last time. The writer session state memory is a limited resource and writers must eventually reuse session states. This step marks the writer’s backup session state as completed and notifies VSS that this backup session slot can be reused by a subsequent backup operation.

## Requester Actions during Backup of Files

As noted in [Overview of the Backup Discovery Phase](overview-of-the-backup-discovery-phase.md), you should not generate the actual list of files to be backed up until the shadow copy has completed.

The [*device object*](vssgloss-d.md#base-vssgloss-device-object) corresponding to the shadow copy of a given volume is used to get access to files on the shadow copied volume once the shadow copy has completed. The device object is obtained from the [**VSS\_SNAPSHOT\_PROP**](/windows/win32/Vss/ns-vss-_vss_snapshot_prop?branch=master) object returned by [**IVssBackupComponents::GetSnapshotProperties**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-getsnapshotproperties?branch=master). Each shadow copy of a shadow copy set will have its own device object.

The device object and the paths obtained from the Writer Metadata Document specifications of components are then used to select files for backup. See [Requester Access to Shadow Copied Data](requestor-access-to-shadow-copied-data.md) for more information.

Which files will be included in the backup list depends on the nature of the particular backup, upon component [*selectability for backup*](vssgloss-s.md#base-vssgloss-selectability-for-backup), and the logical path structure of the writer (see [Working with Selectability for Backup](working-with-selectability-for-backup.md)).

In addition to files specified in the components, a given writer may also have explicitly excluded files. File exclusion must always be respected, regardless of which components are selected.

Also as noted in [Overview of the Backup Discovery Phase](overview-of-the-backup-discovery-phase.md), a mounted folder or reparse point can appear in a shadow copy and can be backed up. However, a mounted folder or reparse point cannot be traversed on the shadow-copied volume (see [Working with Mounted Folders and Reparse Points](working-with-reparse-and-mount-points.md)).

Care should also be taken during a backup operation, if the [*alternate path*](vssgloss-a.md#base-vssgloss-alternate-path) returned by [**IVssWMFiledesc::GetAlternateLocation**](/windows/win32/VsWriter/nf-vswriter-ivsswmfiledesc-getalternatelocation?branch=master) is not blank. An alternate path differs from an [*alternate location mapping*](vssgloss-a.md#base-vssgloss-alternate-location-mapping) in that it is used only during backups, while an alternate location mapping is used only during restores.

In this case, the data is not to be backed up from its normal location (indicated by [**IVssWMFiledesc::GetPath**](/windows/win32/VsWriter/nf-vswriter-ivsswmfiledesc-getpath?branch=master)), but from the location returned by [**IVssWMFiledesc::GetAlternateLocation**](/windows/win32/VsWriter/nf-vswriter-ivsswmfiledesc-getalternatelocation?branch=master). On restore, the file should be returned to its normal location. See [Non-Default Backup and Restore Locations](non-default-backup-and-restore-locations.md) for more information.

VSS places no restrictions on the actual mechanism of backing up data to a storage medium or the choice of that medium. However, it is recommended that the files of each component of each [*writer instance*](vssgloss-w.md#base-vssgloss-writer-instance) be processed as a unit. See [Generating A Backup Set](generating-a-backup-set.md) for a discussion of best practices in generating the backup file list.

The success or failure of backing up any of the files managed by a given component and (if it defines a [*component set*](vssgloss-c.md#base-vssgloss-component-set)) its [*subcomponents*](vssgloss-s.md#base-vssgloss-subcomponent) for a given writer instance should be preserved in the Backup Components Document by calling [**IVssBackupComponents::SetBackupSucceeded**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-setbackupsucceeded?branch=master). If any file managed by a component or component set fails to back up, the entire component is said to fail. Exact information about which file failed to back up should always be logged.

Developers may find it helpful to store a record on the backup media of which files are backed up, the components and component set they were a member of, their specification, and what their original paths were. It may also be useful to store information such as each writer's component definition. Doing this may make the retrieval operation simpler. However, such details are left to the requester developer.

Because writers can modify the Backup Components Document while handling the [**PostSnapshot**](/windows/win32/VsWriter/nf-vswriter-cvsswriter-onpostsnapshot?branch=master) event generated by the requester's call to [**IVssBackupComponents::DoSnapshotSet**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-dosnapshotset?branch=master), the Backup Components Document should not be saved until after that asynchronous call has completed.

Although it may take place earlier, this is also a convenient time to save the Writer Metadata Document.

It is very important that both the Backup Components Document and the Writer Metadata Documents be preserved using [**IVssBackupComponents::SaveAsXML**](/windows/win32/VsBackup/nf-vsbackup-ivssbackupcomponents-saveasxml?branch=master) and [**IVssExamineWriterMetadata::SaveAsXML**](/windows/win32/VsBackup/nf-vsbackup-ivssexaminewritermetadata-saveasxml?branch=master). If they are not, it will not be possible to make use of VSS during file restoration.

In addition to storing the original metadata, some backup applications may find it useful to save a copy of their own list of the files (in their own optimized format)—and their associated writer, component, restore procedure, and location information—to the backup media for later retrieval. Such a list can be used to avoid some of the parsing and comparing of Writer Metadata Documents and the Backup Component Documents during restore.

Volumes being backed up may have data that is not managed by VSS writers. This data can and should be backed up from the shadow copied volume, where it will be in a [*crash-consistent state*](vssgloss-c.md#-win32-vssgloss-crash-consistent-state). See [Backups without Writer Participation](backups-without-writer-participation.md) for more information.

 

 



