# rmarkdown_syllabus

This repository shows an example of an R markdown script (syllabus.Rmd) that reads in a csv file of lecture titles and readings and turns it into a formatted syllabus. The script will generate all dates, all you need is the first day of class. In addition, you can add in holidays and conference trips which are easily integrated into the schedule. 

- the syllabus produced from this script is for my INR 4075: International Human Rights course at FSU. 

# How to use 

1. Download **syllabus.Rmd** and **template.tex** 
2. Create a .csv file with lectures and readings. This repository includes an example: **lectures.csv**. You can create as many readings as you want. For example, if you want to include a third reading for some weeks, insert this code between the second reading if statement and the else statement. 
  
  <code>  
         if(lectures$Reading3[lecture.count]!=""){
               
               cat('  \n')
               print(bib[lectures[lecture.count, "Reading3"]])
               cat('  \n', '   \n', '   \n') 
               
          }
  </code>
  
3. Create a .bib file with BibTex entries for all readings. Also include `@misc` bib entries for final exam and midterm and any movies you may show (this is necessary, for now, to include this in the schedule). This repository includes an example: **readings.bib**.  
4. Edit the YAML and course policies to suit your course. 
5. Change `firstday`, `missing.days`, `calendar` settings to fit your course. 
6. Knit the **syllabus.Rmd**. My preference is to knit this to pdf. The script will knit to html and word but formatting is different and some of the bib entries to not convert as well as they do in the pdf version. 


# Output 

These scripts produce **syllabus.tex** and **syllabus.pdf**. 


# Currently (when possible) tweaking

1. Somehow integrating exams and movies without having to use bib entries. 
2. Allowing for blank lectures (as of now the code do not run unless the number of lectures and missing days matches the total number of days) 

If you have any suggestions or questions please fill free to reach out to me <a href="mailto:kfruge@fsu.edu">here</a>
