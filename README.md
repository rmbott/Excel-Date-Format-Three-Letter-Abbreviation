# Excel-Date-Format-Three-Letter-Abbreviation
# Ryan M. Bott
#An Excel function takes an Excel date and yields that date in a three letter abbreviation format. (e.g. "Mon. Jan. 1st") This format is handy for postcard invitations, where space is limited and the first thing you think when you see the date is "What day of the week is that?" or "Is that a weekend?". As of the creation of this repository, MS Excel does not have a built in date format like this.

# To refer to a cell with a date in it, replace the references to "TODAY()" with a reference to that cell.

# This function is currently not compatible with LibreOffice because of a restriction on the number of parameters allowed in the CHOOSE() function. If you come up with a workaround for that restriction, let me know.


=CONCATENATE(
	CHOOSE(
    WEEKDAY(TODAY()),
      "Sun.","Mon.","Tue.","Wed.","Thu.","Fri.","Sat."),
      " ",
	  CHOOSE(
      MONTH(TODAY()),
      "Jan.","Feb.","Mar.","Apr.","May.","Jun.","Jul.","Aug.","Sep.","Oct.","Nov.","Dec."),
      " ",
    CHOOSE(
      DAY(TODAY()),
      "1st","2nd","3rd","4th","5th","6th","7th","8th","9th","10th",
      "11th","12th","13th","14th","15th","16th","17th","18th","19th",
      "20th","21st","22nd","23rd","24th","25th","26th","27th","28th","29th",
      "30th","31st"
  )
)

