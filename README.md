# Reduce Amazon Mechanical Turk's 40% fee to 20%

## Instructions

1. Create a new project, fill in all the details as normal.
2. Set the number of assignments per HIT at 1.
3. I like to require at least a 90% acceptance rate and 100 approved HITs.
4. Replace the source code of the description with [this](html_source_for_HIT.html) code.
5. Upload a csv file. Sample here.


## How it works

The important line of the HIT code is `<!--${filler}-->` which indicates to Amazon that you are going to provide a csv file that has a list of all the HITs to create, each with a different value for the variable `filler`.

But these variables don't ever show up in the description of the HIT, because they are enclosed within HTML comments.

When you upload the file that has 1 column (header is filler) and N rows with some arbitrary values, Amazon creates a separate HIT for each N row. You are only charged a 20% fee if each of those HITs has fewer than 9 participants.
