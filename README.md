Gnmap-Parser
============
## What's Updated?
This release is based on the version from 2014, and the base functionality remains untouched. The part that changed is the "Host-Type" functions. Now there's a "DomainControllers.txt" file and the "Printers.txt" is updated with additional printer ports and one of the original regex searches was incorrect, which prevented an accurate list of printers. Finally, the well-known "Parsed-Results" folder has a date-time stamp appended for those times when you're running multiple parsing jobs on a single engagement and need to know when a port was first observed without overwriting folders/files. 

Description
-----------
Gnmap-Parser takes multiple Nmap scans exported in greppable (.gnmap) format and parses them into various types of plain-text files for easy analysis.

**Parsing Formats Include:**

* Alive Hosts List Based on ICMP Replies
* Alive Hosts List Based on Open Ports
* Host Type Lists Based on Open Ports
* Simple TCP/UDP Ports Lists Showing Unique Open Ports Discovered Across All Hosts
* Port Files In "[#]-[TCP/UDP].txt" Format Consisting of Ordered Hosts
* CSV Style Port Matrices In "[HOST],[PROTOCOL],[PORT]" Format
* Third-Party Tool Input File Formats (Currently: PeepingTom)

Usage
-----
**Supported Switches:**

* -g  = Gather .gnmap files (faster but only finds files with .gnmap extension).
* -gg = Heuristically gather .gnmap files (slower but finds files regardless of extension).
* -p  = Parse .gnmap files.

**Limitations:**

* Gnmap-Parser will only parse *.gnmap files that are in the same directory that it resides. For this reason, the gather switches (-g) and (-gg) were 
implemented to copy .gnmap files from their known locations into the scripts working directory. Any path will work as Gnmap-Parser will traverse all
subdirectories. For instance, providing a parent directory of "/" will traverse the entire root filesystem looking for *.gnmap files.

* Gnmap-Parser currently only parses files that end with the .gnmap extension. If using the -oA switch of Nmap, these files will already
be named with the correct extension. If specifying the -oG switch, be sure to append .gnmap to the filename or use the (-gg) switch.
