# TOPS20-MODEM
The TOPS20 implementation of X/Y/ZModem, as used at SIMTEL-20.

## History of X/Y/ZModem

In the dawn of the personal computer age, Ward Christensen developed a protocol and utility
to allow personal computer users to exchange files over phone lines using dialup links.  Or
locally over UART-based serial ports.  Before Internet, before "thumb drives", before there were even
common shared floppy disk formats, such file transfers were an important way for users to share software
(OSSW, but it wasn't called that in those days), data, and so on.

The MODEM (somtimes MODEM2?) protocol transmitted a 128 byte block at a time, with checksum and positive or
negative acknowlegement.  You'd set up a transmitter at one end of the connection "MODEM S myfile.txt", and
then start a receiption at the other end "MODEM R file1.txt"

The was enhanced, producing the YMODEM protocol.  The checksum was replaced with a CRC, and the transmitted
passed filename info at the beginning of the transfer.  This permitted "MODEM S *.txt" on the sender, and just
"MODEM R" on the receiver (assuming the wanted to keep the filenames the same.)

ZMODEM added larger packets, and a sliding window scheme that dramatically increased throughput.

## X/Y/ZModem on Mainframes

The (minority) community with access to larger computers - "mainframes" and "minicomputers" had desire
to use those systems for storage, and MODEM compatible utilities for several such systems were also written.
Some of those larger systems were connected to larger computer networks (like the ARPANet), so it wasn't an
uncommon use-case to write some software on a CP/M system, upload it using MODEM to a school mainframe, transfer
it over ARPANet FTP to someone else who was interested, and then download it to their microcomputer.

I wrote a primitive MODEM utility for the DEC PDP-10 running TOPS-10 while I was a student at University of
Pennsylvania.  https://groups.google.com/g/fa.info-cpm/c/GCa7OAG_r-M
When I graduated and went to work at SRI (1981), one of the things I wrote was a more advanced version for DEC's
TOPS-20 mainframes.  It was done by the time the original IBM PC was introduced, and which point more and more
users were interested in transfering files to and from the mainframes, and I wrote an easy-to-use client version
for the PC as well.  It was pretty popular, internally, and I made some efforts to "going commercial" with the
client.  I would have been a competitor of CrossTalk version 1, if things had gone well.  (Things did NOT go well,
so no one has ever seen that software.  Sigh.)

## Simtel-20

In a similar timeframe, Frank Wancho talked the Army into creating SIMTEL-20.  The idea was that US military users
with personal computers would have a single trusted site where they could download the Free and Shareware software
(OSSW), instead of having to search random places that perhaps weren't so trustworthy.  Simtel-20 was another
DEC Tops20 system (they were pretty popular on the ARPANet), located at White Sands Missile Range, and it ran my MODEM
software as its main download
utility.  (Frank both motiated and made additional enhcanements to the program.)
At one point, Simtel20 host the entire CP/M User Group software collection, as well as a similar collection
of MSDOS software.   I think you can still get "SIMTEL-20 Software Collection" CDs.  (Interesting Trivia: a single CD
has about the same storage capacity as the washing-machine-sized RP07 Disk Drive that was frequently connected to Tops20 systems.)

And that's an example of how allowing students who really should not have access to the ARPANet ended up being
good for the people who WERE the proper users of the ARPANet.  :-)
