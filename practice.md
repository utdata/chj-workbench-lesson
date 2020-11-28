# Workbench practice with opioid deaths

I'll often have students read over these [Tips for exploring new datasets](https://docs.google.com/document/d/1ql3NcPihfTsWb5qFxWIxthybpSvFh_cAcPuMi1McM_0/edit?usp=sharing). You might look over it for some concepts and ideas.

The data here are opioid deaths in Minnesota from 2005 to 2017. Each row is a death, with columns that describe the person.

## Importing the data

You can use **Import by URL** and use this:

`https://github.com/utdata/chj-workbench-lesson/blob/master/data/chj_mn_opiate_deaths_data.csv?raw=true`

## Data cleaning

There are several columns that could use cleaning.

- Convert the date fields to real dates.
- You might make a copy of RACE and use **Refine** to merge into more narrow categories: White, Black, Asian, American Indian, Other.
- You could rename the values in Gender if you wanted to.

## Group and aggregate

### Cases per year

How many cases per year? There are different ways to go about this, and I admit this is more convoluted than pivots in Excel, but it works.

- Duplicate the DEATHDATE.
- Use **Split by timestamp** using **Year** and name it "YEAR".
- After the split, you have to use **Convert to text** on the new column, and then use **Clean text** to remove the comma.
- Use Group on `Year` and count the rows.

### Cases per [Insert column here]

There are tons of categorical data here for each case that you could group on. Some options:

- By RACE and/or HISPANICETHNICITY
- By GENDER
- By AGEYEARS
- By RESCITY, RESCOUNTY or ZIP

And basically every other category in the data.

You might also try grouping by more than one column, like race and the year.
