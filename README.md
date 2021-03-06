# ID Badges

This tool takes a folder of pictures and an excel sheet of TA names and class assignments, and outputs printable TA ID badges.

This tool is built to work with the provided "nametagTemplate.png". Follow these instructions exactly, and it will generate the PSR nametags.

TA pictures need to be named as "FirstLast.jpg". The First and Last names must
be the same as the ones in the Excel document. Make sure each name is capitalized in the filename.

# To use the tool:

0. Install xlrd, xlsxwriter, and Pillow. This can be done using pip by running the following:

		pip install xlrd
		pip install xlsxwriter
		pip install Pillow

1. Place the BadgeMake.py, nametagTemplate.png, and the info.xlsx files into a
 folder.
 	* The file info.xlsx should have TA names in first column ( formatted: {First} {Last} ) and
 the course they TA in the second column ( formatted: {Subject} {Number} ). There should be no headers.

2. Make the subfolders "Output" and "Pictures".

3. Place all the TA pictures in the Pictures folder.
	* Make sure they are all in the correct format (FirstLast.jpg).

4. Run BadgeMake.py using run.bat. This will take ~10 seconds.

5. The completed badges will save to the Output folder.

	* Names which cause errors (largely, through missing pictures) will be
	written to errors.txt in the Output folder.

# To print multiple badges per page:

1. Navigate in Explorer to the Output folder.

2. Select all pictures (Ctrl + A).

3. Right click and choose "Print".

4. From print window, select appropriate printing option along right edge.

# Use-Specific: UCSB PSR TA Badges

Open the Excel document provided by the department of the active TAs.

The Excel workbook provided by the department is messy. Fix it by doing the following:

## Removing non-PSR Entries:

Not all of the people on that list need a badge. There may be other courses which do not require a badge, but are not eliminated from by the following steps. Check with the department admin to get an updated list of the courses which need badges.

1. Delete all reader names (beige highlight).

2. Delete all CCS names (yellow highlight).

3. Delete all PSR fellow names (at bottom).

At the time of writing, the other courses/roles which do not need tags are Physics 127A-B, 128A-B, 129, 13BH, 260J, and 25L.

## Fix Course Numbers:

The default organization only labels Course Number on the first TA (sometimes first 2+) to appear in the list of TAs for a particular course.
Additional TAs for the same course will be placed beneath the labeled TA, and will have their Course Numbers blank.

1. For each labeled TA with unlabled TAs below them, copy their course assignment downward into the blank spots immediately below them.

## Generate info.xlsx (holds TA data for tag generation):

1. Create new excel document, info.xlsx, in the same folder as the BadgeMake file.

2. Copy the column with the TA names and the column with the Course Numbers, and paste them to columns C and D of info.xlsx.

3. Resolve Multi-class Assignments:

	* The tool cannot handle duplicate entries -- where a TA is serving for multiple classes.

	* Alphabetize by name to identify duplicates. If a TA is serving two courses, combine entries to one row with Course Number as "PHYS #, #".

4. Delete row 1. There should be no headers for the columns.

5. Reformat Course Numbers.

6. Reformat Names: The default organization only labels Course Number on the first TA (sometimes first 2+) for a particular course. Additional TAs for the same course will be placed beneath the labeled TA, and will have their Course Numbers blank. Copy these to the entries below before changing any ordering on the spreadsheet.

	* Reformat names to "{First} {Last}".

7. The info.xlsx file should now be formatted as:

	* First column: TA Names

				Format: "First Last"

	* Second column: Course Number

				Format: "Phys #"

				(If serving multiple courses, Format: "Phys #, #")
				
8. Run tool to generate badges. See "To Use the Tool" for details.
