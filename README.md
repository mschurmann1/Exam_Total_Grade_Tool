# Exam Total Export

A browser tool that combines a Canvas gradebook export (with written exam scores entered by hand) and a WeBWorK totals file (with the exam's practice problem set), then fills two Canvas columns ready to import:

1. **Practice Problems**, on a 10 point scale (for example, 20 out of 20 in WeBWorK becomes 10).
2. **Etotal** = Written + Practice Problems + Extra Credit (for example, 90 + 10 + 3 = 103).

## Privacy

All files are read and processed entirely in the browser. No gradebook or WeBWorK data is uploaded, stored on a server, or committed to this repository. The `.gitignore` blocks CSV and Excel files as an extra safeguard.

## What you need

1. **Canvas gradebook export** (Grades, Export, Export Entire Gradebook), exported after the written exam scores are entered. The Practice Problems and Etotal columns must already exist in Canvas.
2. **WeBWorK totals file** (Scoring Tools, Pad fields unchecked, the file ending in `totals.csv`) including the practice problem set.

## How scores are calculated

* **Practice Problems:** WeBWorK set total ÷ set value × 10, rounded to two decimals. The scale can be changed.
* **Etotal:** written score + practice problem points + every checked extra credit column. Blank or EX extra credit counts as 0.

Etotal is left untouched when the written score is blank or EX, or when the student has no practice problem score. Any Practice Problems or Etotal cell already marked EX stays EX. A report lists every cell not entered and why.

## Canvas setup

Put the Written, Practice Problems and extra credit columns in an assignment group worth 0%, and the Etotal columns in the exam group, so nothing is counted twice.

## Updating the tool

Replace `index.html` with the new version through the GitHub website. GitHub Pages republishes automatically within a few minutes.
