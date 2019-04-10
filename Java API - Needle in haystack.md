   *getNeedles(String haystack, String[] needles)*

The  `getNeedles`  method receives two parameters, a haystack string and an array of needles. This method retrieves the instances of the strings from the needles array within the haystack string and then outputs any matches with the number of occurrences.

# Public methods

  *public static void getNeedles (String haystack, String[] needles)*

Searches the haystack string for strings in the needles array.    

    String [] needles = {“needles”, “TEST”, “my”};
    String haystack = “these\rare\nMY\rTEST\tneedles”;
    
    getNeedles(haystack, needles);

Parameters

| Parameter | Type | Description |
| ---- | ---- | ----| 
| haystack | String | A string of strings separated by \”\’\n\r\t\b\f delimiters |
| needles | String[] |  Array of strings to search for in the haystack string |



# Optimizations

## Memory enhancements

1. Move the creation of the words array outside of the loop as this only needs to be created once
2. Create a string containing the escape characters to split the string once and store it outside the loop rather than creating it each time the split method is called

## Enhanced features

1. Add an extra parameter for the MAX needles instead of using a magic number
2. Add a Boolean parameter to offer the option to ignore the case of both the needle and the haystack

## Modified Code

     /**
      * findNeedles
      * This method is used to locate the needles within an array of strings
      *
      * @param String haystack – String containing multiple words
	  * @param String [] needles – Array of strings to be searched for within the haystack
      * @param boolean ignoreCase -boolean value to ignore the case of the strings in both
      * the needle and the haystack
      * @param int maxWords – integer value for the max number of words permitted in the haystack
      */
	 public static void findNeedles(String haystack, String[] needles, intmaxWords, booleanignoreCase) {
    	if(needles.length> maxWords) {
		    System.err.println("Too many words!");
		} else {
		    int[]countArray= newint[needles.length];
		   /** 
		    * Create a string containing the escape characters to split the string
		    * once and store it outside the loop rather than creating it each time the split
		    * method is called
		    */
		    String delimiters= "[ \"\'\t\n\b\f\r]";
		    
		    /**
		     * Generate only one instance of the array of words outside the loop by 
		     * splitting the haystack string, separating each word with any of the
		     * following escape sequences: double quote, single quote tab, new line,
		     * backspace, form feed.
		     * /
		    String []  words=  haystack.split(delimiters, 0);
		    
		    /** Loop through the needles array */
		    for(inti=0;i<needles.length;  i++) {
			    for(intj=0;j<  words.length;  j++) {
	    			if(ignoreCase) {
		    			/** 
		    			 * ignoring case so convert both the word and the needle to lowercase 
		    			 */
	    				if((words[j].toLowerCase()).compareTo(needles[i].toLowerCase()) ==0) {
	    					countArray[i]++;
	    				}
	    			}  else {
	    				if(words[j].compareTo (needles[i]) ==0) {  countArray[i]++;
	    			}
	    		}
	    	}

		for(intj=0;j<needles.length;  j++) {
		    System.out.println(needles[j] +  ":"+  countArray[j]);
		}
	}	


