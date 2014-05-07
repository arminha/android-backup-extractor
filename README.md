Android backup extractor
========================

Utility to extract and repack Android backups created with ```adb backup``` (ICS+).
Largely based on BackupManagerService.java from AOSP.

Build
-----

 - Create abe.jar with ```./gradlew build```

 - Create an archive including all libraries and shell scripts to start abe with ```./gradlew distZip```

Usage
-----

_abe_ in this example refers to the shell script created with ```./gradlew distZip```

Syntax:

	unpack:	        abe unpack  <backup.ab> <backup.tar> [password]
	pack:	        abe pack    <backup.tar> <backup.ab> [password]
	pack for 4.4:	abe pack-kk <backup.tar> <backup.ab> [password]

If you don't specify a password the backup archive won't be encrypted but
only compressed.

Alternatively abe can also be started through gradle with ```./gradlew run```.

More details about the backup format and the tool implementation in the 
associated blog post: 

http://nelenkov.blogspot.com/2012/06/unpacking-android-backups.html

