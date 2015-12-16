# translateDna
Quickly translate DNA in chosen frame and optionally line up translation and DNA sequence

##Install

This is a commandline program written in perl. To install download the zip file from the git repository (https://github.com/gantzgraf/translateDna) or clone the repo:

    git clone https://github.com/gantzgraf/translateDna.git 

From the unzipped/cloned translateDna directory simply run the script like so to get usage information:

    ./translateDna.pl -h 

Or alternatively: 

    perl translateDna.pl -h

##Examples

Input files may be plain text or FASTA format. The following will translate all sequences in the FASTA formatted file 'dna_input.fa'. 

    ./translateDna.pl -i dna_input.fa

You may wish to output your dna input aligned with your translated sequence...

    ./translateDna.pl -i dna_input.fa -d 

...and number your output...

    ./translateDna.pl -i dna_input.fa -d -n 

You may want to specify a different translation frame:

    ./translateDna.pl -i dna_input.fa -f 2

You may want to stop at the first termination codon encountered:

    ./translateDna.pl -i dna_input.fa -s 

You can also supply input from STDIN by specifying '-' as your input file, like so: 

    ./translateDna.pl -i - 
    
In this way you may pipe output from other programs, for example: 

    curl http://genome.ucsc.edu/cgi-bin/das/hg19/dna?segment=chr11:45827392,45827904  | grep -v '<' | ./translateDna.pl -i - 

For an explanation of all options use the -h option:

    ./translateDna.pl -h 


##Credit

Copyright © 2015  David A. Parry

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see <http://www.gnu.org/licenses/>.

