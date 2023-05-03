Download Link: https://assignmentchef.com/product/solved-cs342-operating-systems-project-1-processes-and-threads
<br>
You will do this project individually. You have to program in C  and Linux. You are required to use the following distribution of Linux: <strong>Ubuntu 16.04 – 64 bit</strong>.




<h1>Part A: Processes [35 points]</h1>

<em><u>Objective</u>: Practice process creation, developing multi-process applications, file I/O, statistics. </em>

<em> </em>

In this part, you will develop a <strong>multi-process</strong> application that will generate a value histogram for the values sitting in a set of input ascii text files, one value per line. Values can be an integers or real numbers. The program will be called <strong>phistogram </strong>and will take the following parameters:




<strong>phistogram</strong><em>  minvalue  maxvalue bincount N  file1 … fileN outfile </em>




Here,  <em>minvalue</em> is the minimum value that exists in the given set of input files, and <em>maxvalue</em> is the maximum value. <em>bincount</em> is the number of bins in the histogram. Let <em>w</em> denote bin-width. Then w = (<em>maxvalue</em> – <em>minvalue</em>) / <em>bincount</em>.  The first bin will give the count of values in range [<em>minvalue</em>, <em>minvalue+w</em>); the second bin will give the count of values in range [<em>minvalue+w</em>, <em>minvalue+2w</em>); and so on. <em>N</em> is the number of input files. <em>file1</em> … <em>fileN</em> are the names of  these input files. <em>outfile</em> is the output file.

Your program will create another child process for each input file to generate a histogram for the values in that input file. Hence there will be <em>N</em> child processes working concurrently on the <em>N</em> input files, and at the end, <em>N</em> histograms will be generated into <em>N</em> intermediate files. The parent  process will then combine these <em>N</em> histograms into one histogram  and will output this histogram to the output file. Each output line will contain information about a separate bin in the following format: <em>binnumber</em>: <em>count</em>. Binnumbers will start at 1.

<strong> </strong>

<h1>Part B: Threads  [35 points]</h1>

<em><u>Objective</u>: Practice developing multi-threaded applications.  </em>

<em> </em>

In this part, you will develop the same application described in part A using threads. For each input file, there will be a separate worker thread. Each worker thread will generate the histogram of the corresponding input file values into a global data structure in memory.  Then the main thread will read those histograms  from these structures and will generate a single histogram and will print that out to the output file. The program will be called <strong>thistogram</strong>.




<h1>Part C: Experiments [30 points]</h1>

<em><u>Objective</u>: Practice designing and conducting experiments and applying knowledge and skills acquired in the Probability and Statistics course.  </em>

<em> </em>

Do some timing experiments to answer the following questions.

1




<ol>

 <li>What is the running time of your multi-process application for 1, 2, 4, 8 processes working together for the same input? What it the running time of your multi-treaded application?</li>

 <li>Consider a 2 process (or 2 thread) application. What is the running time for various values of input size?</li>

</ol>




<h1>Submission</h1>

<strong> </strong>

Put all your files into a project directory named with your ID,  tar the directory (using <strong>tar xvf</strong>), zip it (using <strong>gzip</strong>) and upload it to Moodle.  For example, a student with ID 20140013 will create a directory named 20140013, will put the files there, tar and gzip the directory and  upload the file. The uploaded file will be  20140013.tar.gz. Include a <strong>README.txt</strong> file as part of your upload. It will have your name and ID at least. Include also a <strong>Makefile</strong> to compile your programs. We want to type just <strong>make</strong> and obtain the executables.  Do not forget to put your report  (PDF form) into your project directory.




<h1>Additional Information and Clarifications</h1>




<ul>

 <li><em>Suggestion: work incrementally; step by step; implement something, test it, and when you are sure it is working move on with the next thing. </em></li>

 <li>More <strong>clarifications</strong>, additional information and explanations that can be useful for you may be put to the <strong>course website</strong>, just near this project PDF. Check it regularly. <em> </em></li>

 <li>You can use Piazza for questions and discussions.</li>

 <li>The objective in this project is not to see a speed-up by use of multiple processes or threads. The objective is to practice use of multiple processes and threads.</li>

</ul>

<em> </em>

2