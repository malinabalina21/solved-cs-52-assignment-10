Download Link: https://assignmentchef.com/product/solved-cs-52-assignment-10
<br>
<section id="cs-52-assignment-10" class="level1">

 <h1><span style="font-size: 2em;">Project 1 – Pointers Continued (Sudoku)</span></h1>

 <section id="project-1---pointers-continued-sudoku" class="level2">

  The purpose of this assignment is to practice dealing with string data. The goal is to work with data declared as <code>char *</code>(C-string) and also as <code>string</code>. I think you’ll like working with strings much better. Please recall that string is officially known as <code>std::string</code>.




  <section id="sudoku-row-checker" class="level3">

   <h3>Sudoku Row Checker</h3>

   Sudoku is a logic-based number placement puzzle. The objective is to fill a 9×9 grid so that each column, each row, and each of the nine 3×3 boxes (also called blocks or regions) contains the digits from 1 to 9 only one time each. For those of you not familiar with this game, you can learn more about it here: <a class="uri" href="https://en.wikipedia.org/wiki/Sudoku">https://en.wikipedia.org/wiki/Sudoku</a>

   The Sudoku Row Checker class is can be used to validate a string of information. Using string operations, it should verify that each number 1 to 9 is used only one time. Following the class specifications shown below, implement the Sudoku Row Checker class. Implement a suitable testing suite asides from the ones already provided that proves your calculations are correct. You may choose to create any number of additional methods, but you are required to implement all of the public methods shown below.

   <section id="sudokurowchecker" class="level4">

    <h4>SudokuRowChecker</h4>

    <pre class="cpp"><code>public:  SudokuRowChecker( );  // same function name, but with different arguments. You must implement both versions of the setData() function.  void setData( const char * s );  void setData( std::string s );  void clear();  bool isValid( ) const;private:  string sudokuRow;</code></pre>

   </section>

  </section>

  <section id="sample-testing-driver-code" class="level3">

   <h3>Sample Testing Driver Code</h3>

   <pre class="cpp"><code>    // test 1, invalid string    SudokuRowChecker c1;    std::string s1 = "12345678901";    c1.setData(s1);    if(c1.isValid()){        std::cout &lt;&lt; "1.1. Invalid string, 11 characters string; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "1.1. Invalid string, 11 characters string; test passed" &lt;&lt; std::endl;    }        // test 2, invalid c-string    SudokuRowChecker c2;    std::string s2 = "12345678901";    c2.setData(s2.c_str());    if(c2.isValid()){        std::cout &lt;&lt; "2.1. Invalid string, 11 characters c-string; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "2.1. Invalid string, 11 characters c-string; test passed" &lt;&lt; std::endl;    }        // test 3, make sure checker is considered invalid after default constructor    SudokuRowChecker c3;    if(c3.isValid()){        std::cout &lt;&lt; "3.1. Invalid string, empty string after initialization; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "3.1. Invalid string, empty string after initialization; test passed" &lt;&lt; std::endl;    }        // test 4, make sure checker is considered invalid after setting empty string    SudokuRowChecker c4;    string s4 = "";    c4.setData(s4);    if(c4.isValid()){        std::cout &lt;&lt; "4.1. Invalid string, empty string; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "4.1. Invalid string, empty string; test passed" &lt;&lt; std::endl;    }        // test 5, make sure checker is considered invalid after setting empty string    SudokuRowChecker c5;    char s5[] = "";    c5.setData(s5);    if(c5.isValid()){        std::cout &lt;&lt; "5.1. Invalid string, empty c-string; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "5.1. Invalid string, empty c-string; test passed" &lt;&lt; std::endl;    }        // test 6, make sure checker is considered valid with correct string    SudokuRowChecker c6;    string s6 = "123456789";    c6.setData(s6);    if(c6.isValid()){        std::cout &lt;&lt; "6.1. Valid string; test passed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "6.1. Valid string; test failed" &lt;&lt; std::endl;    }        // test 7, make sure checker is considered valid with correct string    SudokuRowChecker c7;    char s7[] = "123456789";    c7.setData(s7);    if(c7.isValid()){        std::cout &lt;&lt; "7.1. Valid string; test passed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "7.1. Valid string; test failed" &lt;&lt; std::endl;    }        // test 8, invalid, string shorter than it should be    SudokuRowChecker c8;    string s8 = "1234";    c8.setData(s8);    if(c8.isValid()){        std::cout &lt;&lt; "8.1. Invalid string, string too short; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "8.1. Invalid string, string too short; test passed" &lt;&lt; std::endl;    }        // test 9, invalid, string shorter than it should be    SudokuRowChecker c9;    char s9[] = "1234";    c9.setData(s9);    if(c9.isValid()){        std::cout &lt;&lt; "9.1. Invalid string, string too short; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "9.1. Invalid string, string too short; test passed" &lt;&lt; std::endl;    }        // test 10, invalid, correct length, duplicate characters    SudokuRowChecker c10;    string s10 = "000000008";    c10.setData(s10);    if(c10.isValid()){        std::cout &lt;&lt; "10.1. Invalid string, duplicate characters in string; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "10.1. Invalid string, duplicate characters in string; test passed" &lt;&lt; std::endl;    }        // test 11, invalid, correct length, duplicate characters    SudokuRowChecker c11;    char s11[] = "000000008";    c11.setData(s11);    if(c11.isValid()){        std::cout &lt;&lt; "11.1. Invalid string, duplicate characters in c-string; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "11.1. Invalid string, duplicate characters in c-string; test passed" &lt;&lt; std::endl;    }        // test 12, check clear    SudokuRowChecker c12;    char s12[] = "123456789";    c12.setData(s12);    c12.clear();    if(c12.isValid()){        std::cout &lt;&lt; "12.1. Invalid string, clear() should empty data; test failed" &lt;&lt; std::endl;    } else {        std::cout &lt;&lt; "12.1. Invalid string, clear() should empty data; test passed" &lt;&lt; std::endl;    }    return 0;</code></pre>

  </section>

 </section>

</section>

<section id="codeboard-submission" class="level2">

 <h2>Codeboard Submission</h2>

 Please refer to the codeboard submission instructions here: <a href="http://mjedmonds.com/CS50/codeboard.html">http://mjedmonds.com/CS50/codeboard.html</a>

</section>