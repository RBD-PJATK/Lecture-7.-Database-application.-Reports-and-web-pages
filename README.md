# Lecture 7. Database application. Reports and web pages

<h3>Abstract</h3>

<p>In lecture 7 we describe more objects of the user interface of a database
application: reports and web pages.</p>
  
<p>Reports are used to present the data from a database. 
They are read-only.  Reports as well as forms belong to a user's view.
A report is usually based on a query (or a table) that defines the range of data
to be displayed. The definition of a report is developed and presented in 
<i>the design view</i>. The content of the report is shown in 
<i>the print preview</i> and then may be saved in the form of the document
for MS Word or MS Excel.</p> 

<p><i>Data access pages</i> are interactive web pages that have 
an active connection to MS Access. The user selects such a page in Microsoft 
Internet Explorer (its version must be at least 5) and can view, search and
edit the persistent data stored in the database. Data access pages can be used
in intranets and the Internet.  In the latter case a web server must be used
(e.g. Microsoft Internet Information Server).  It acts as the intermediary
between the browser and
an instance of MS Access running in the local network.</p>

<hr><h3><a name="Raport">Report</a></h3>

<p><i>A report</i> is a presentation of the information prepared by a
database application.  It has the form of a document rendered on the screen.
It can also be printed on paper.  Information presented by a report usually
is taken from a database.  It can be a set of rows directly retrieved from
the database or the same data supplemented by aggregates (for the whole
report, for some groups of records or for each page).  It can also contain
the results of sophisticated mathematical calculations.  Reports usually
contain graphical representations of data like charts and images. The
fundamental assumption about reports is that the user cannot change the copy
of the report displayed on the screen, e.g. he/she cannot add new
records.</p>

<p>The easiest way to obtain a hard copy of the data is to print a form or the 
datasheet of a table or a query.</p>

<p><i>A report</i> is an object of MS Access that is tailored to present
and to recap information in the form of printed documents and documents
displayed on the screen.</p>

<p>You can create reports manually or by means of the wizard.</p>


<hr><h3><a name="Typy">Classification</a></h3>

<h4>Lists, statements</h4>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/6_23.png"></p>

<h4>Catalogs</h4>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/6_22.png"></p>

<h4>Invoices</h4>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/6_21.png"></p>

<h4>Summaries</h4>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/6_19.png"></p>

<h4>Address labels</h4>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/6_20.png"></p>

<hr><h3><a name="Kreatory">Report wizard</a></h3>

<ol>
<li><i>AutoReport</i> (you cannot filter out any fields),
	<ol type="a">
	<li><i>Columnar</i> - each record is rendered as a two-column table
		(the first column is the name of a field; the second column is the value of this field).
	<li><i>Tabular</i> - the data is displayed as a table; each numeric column 
		is summarized at the bottom.
	</ol>
<li><i>Report Wizard</i> - the basic one.
<li><i>Chart Wizard</i>.
<li><i>Label Wizard</i> - labels with addresses to stick to envelopes.
</ol>
 
<hr><h3><a name="Projektowanie">Controls</a></h3>

<p>Rules that drive the design of a report are similar to those 
that concerning forms.
In particular, a report may contain:</p>

<ul>
<li><i>bound elements</i> (they are associated with a column of a table of the database), 
<li><i>unbound elements</i> (they are not associated with a column of a table of the database, e.g. the title of the report) and
<li><i>derived elements</i>.
</ul>
 

<p>Text boxes can be created:</p>

<ul>
<li>by means of the toolbox or
<li>by means of the field list (if you want to open it, select the menu item
	&quot;View -&gt; Field List&quot; or click the button 
	&quot;Field List&quot; on the toolbar).
</ul>

<p>In a report you can use:</p>

<ul>
<li>check boxes,
<li>option buttons,
<li>option groups, e.g. you can set property "Control Source" of a group to
	<blockquote><code>=[Shipment date]&gt;[Receive date]</code></blockquote>
</ul>

<p>The button that move the view to the next page can also be an element of a report.</p>

<hr><h3><a name="Grupowanie">Grouping data in reports</a></h3>

<p>Records can be grouped according to common values of fields.  
For example the records that store the sales from a day may
be grouped together.  One can also add the sum of all the sales
for each day.</p>

<p><i>A group</i> consists of:</p>

<ul>
<li><i>the header</i>,
<li><i>the detail</i> (possibly with nested groups) and 
<li><i>the footer</i>.
</ul>

<p>You define groups in the dialog "Sorting and Grouping" (to open it, choose
the menu item
&quot;View -&gt; Sorting and Grouping&quot;).  Add the grouping column for each desired group and
set the properties &quot;Group Header&quot; and &quot;Group Footer&quot; to "Yes".

<p>You can add some summaries to the footer of the group.  Simply add derived fields with
property "Control Source" set to appropriate aggregate, e.g. <code>=Sum([Name of field])</code> 
to sum up the values of column <code>[Name of field]</code> inside the group.  If you place
such a summary into the footer of the report, you will get the summary of all values
of column <code>[Name of field]</code> inside the report.</p>

<p>Here is an example report with grouping by <i>Id</i> of the department.</p>


<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_1.png"></p>

<p>And here is the design view of this report.  Please notice the structure of:</p>

<ol>
<li>the header of the report,
<li>the header of a page,
<li>the header of group <i>Id</i>,
<li>the detail,
<li>the footer of group <i>Id</i>,
<li>the footer of a page and
<li>the footer of the report.
</ol>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_9.png"></p>

<hr><h3><a name="Podraporty">Subreports</a></h3>

<p>Reports can be nested - a report may contain subreports.  A subreport is a report
itself. It is placed on the main report in the control named "Subform/subreport".</p>

<p>The main report is either unbound or bound to a table or a query.
An unbound report is the container for independent subreports.  Subreport should be 
defined separately with empty headers and footers.  When you put a subreport into
a report, you should define link fields for them (master and detail).  If the linked
tables are connected with a relationship, the system will 
set the link fields automatically.</p>

<p>Subreports may be further nested. A report may also contain subforms</p>

<hr><h3><a name="Zestawienia">Crosstab statements</a></h3>

<p>In offices clerks often use crosstab statements. In such a statement the columns 
as well as the rows are labeled.  These labels are some values taken from the database.
Let us consider the sum of salaries for a particular job in a particular department.
To produce such a summary, we have to transform the data from tables.</p>

<p>We start from the tables <i>Person</i> and <i>Department</i>. In the first step,
we create a query that contains aggregated data for the crosstab statement.
</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_8.png"></p>

<p>In the next step we use the <i>Crosstab Query Wizard</i>.
It prepares a query that has jobs as the labels of the rows and
names of departments as the labels of the columns. At the crossing of
a column (corresponding to a department) and a row (corresponding to a job)
there will be the sum of salaries of all employees with
this job from this department.</p>
 
<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_7.png"></p>

<p>The last step consists in placing the result of this crosstab query on the report.
You can also add the total for each column.</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_6.png"></p>

<p>The crosstab statement in the above report is no longer a table of
the relational data model. This presentation crosses the boundary
of this model.  However, the schemata of the base tables and the logical
level of the database are still fully relational.</p>

<hr><h3><a name="Strony">Data access pages</a></h3>


<p><i>Data access pages</i> are interactive web pages that have 
an active connection to MS Access. The user selects such a page in Microsoft 
Internet Explorer (its version must be at least 5) and can view, search and
edit the persistent data stored in the database. Data access pages can be used
in intranets and the Internet.  In the latter case a web server must be used
(e.g. Microsoft Internet Information Server).  It is the intermediary
between the browser and
an instance of MS Access running in the local network.</p>

<p>There are two kinds of such pages:</p>

<ul>
<li>pages that allow entering new data and editing existing data,
<li>pages that only display data.
</ul>
 
<hr><h3><a name="Stronybez">Page without grouping</a></h3>

<p>This page allows editing.</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_2.png"></p>

<p>Here is the result (after you choose the style for this page).</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_3.png"></p>

<hr><h3><a name="Stronyz">Page with grouping</a></h3>

<p>This page does not allow editing.</p>

<p align="center"><img border="0" src="https://gakko.pjwstk.edu.pl/materialy/2398/lec/wyklad07/images/7_5.png"></p>

<hr><h3><a name="Podsumowanie">Summary</a></h3>

<p>The design of reports and data access pages is similar to the design of forms.
It consists in adding appropriate controls to an object of the graphical user
interface and bounding these controls to tables and views in the database.
In the case of reports and data access pages the basic method to introduce
an internal structure is to group records according to values from one or more columns.
This grouping and <i>crosstab statements</i> are outside of the relational data model.
They are not relations as defined in lecture 5. A report may also present data
as a chart.</p>

<p>Reports may be nested.  A report may contain subforms and subreports.</p>

<hr><h3><a name="Slownik">Dictionary</a></h3>

<dl>
<dt><a href="#Zestawienia">crosstab</a>
<dd>A non-relational table whose rows and columns are labeled. The labels are
	some values stored in the database.
<dt><a href="#Strony">data access page</a>
<dd>An interactive web page that has an active connection to MS Access. 
<dt><a href="#Grupowanie">group</a>
<dd>A method to organize the data in a report. The records are grouped
	according to common values in the grouping columns.
	A group contains its own header, detail and footer.
<dt><a href="#Raport">report</a>
<dd>An object of the user interface that is used to present information from the database.
</dl>

<hr><h3><a name="Zadania">Exercises</a></h3>

<h4>Information</h4>

<p>We continue exercises from lecture 6.</p>

<h4>Exercise 1</h4>

<p>Create report that shows each author and his/her books as well as the number of them.
Use single grouping.</p>  

<h4>Exercise 2</h4>

<p>Create a report that shows each reader together with the books he/she borrowed and the 
number of them.  The information on each book should be supplemented with the list
of its authors.  Use double grouping.</p>
