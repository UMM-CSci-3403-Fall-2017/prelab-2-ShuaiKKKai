# Leak report

The probelm we found is that the code "result = calloc(size-num_spaces+1, sizeof(char));" create a char array each time we call the method strip(), and hadnt free the allocated memory space afte we done with it. We have totaly 5 unfree memory space since we call strip() 5 times when we run the code in main(). By adding a if statement at the end of the method is_cleand(), we free those space. The reason why a if statement is that do to the code we get, the allocated space can be empty, which does not need to be free. 
