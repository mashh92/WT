1----
  <?php
session_start();
if(isset($_SESSION['cnt']))
{
  $_SESSION['cnt']+=1;
}
else
{
$_SESSION['cnt']=1;
}
echo "you have visited the page".$_SESSION['cnt']."times";
echo "<a href=a5_a1.php> click here</a>";
?>


2----
 <?php
echo "style is ".$_GET['s1']."<br>color is ".$_GET['c']."<br>Background color is ".$_GET['b']."<br>size is ".$_GET['s'];
setcookie("set1",$_GET['s1']);
setcookie("set2",$_GET['c']);
setcookie("set3",$_GET['b']);
setcookie("set4",$_GET['s']);
?>

<html>
<body>
<form action="slip21_2_2.php">
<input type=submit value=OK>
</form>
</body>
</html> 

 <?php
$style = $_COOKIE['set1'];
$color = $_COOKIE['set2'];
$size = $_COOKIE['set4'];
$b_color = $_COOKIE['set3'];
$msg = "Welcome to IP";
echo "<body bgcolor=$b_color>";
echo "<font face=$style color=$color size=$size>$msg";
echo "</font></body>";
?>


3----
            <?php
session_start();

if(!isset($_SESSION['count']))
$_SESSION['count']=0;
$username=$_POST['txt1'];
$password=$_POST['txt2'];

			if($username==""&&$password=="")
			  {
					echo"Enter All Details";
                                          
			}

			if($username=="ty"&&$password=="123456")
			{
					echo"login Successfull";
					$_SESSION['count']=0;
			}
                        else 
    		{     
                         $_SESSION['count']=$_SESSION['count']+1;
                      
			if($_SESSION['count']>2)
			{
			echo ("You Exceeded the Limit...ie,3");
			$_SESSION['count']=0;
 			
			}
			else
			{
		echo"Login Failed ... Wrong Details Entered... attempts made:". $_SESSION['count'];
			include('a.html');
			}
		}




?>



4----
<?php
session_start();
$eno = $_GET['eno'];
$enm = $_GET['enm'];
$eadd = $_GET['eadd'];

$_SESSION['eno'] = $eno;
$_SESSION['enm'] = $enm;
$_SESSION['eadd'] = $eadd;
?>

<html>
<body>

<form action="setb2_2.php" method="post">
<center>
<h2>Enter Earnings of Employee:</h2>

<table>
<tr><td>Basic : </td><td><input type="text" name="e1"></td><tr>
<tr><td>DA : </td><td><input type="text" name="e2"></td></tr>
<tr><td>HRA : </td><td><input type="text" name="e3"></td></tr>
<tr><td></td><td><input type="submit" value=Next></td></tr>
</table>
</center>
</form>
</body>
</html>

<?php
session_start();
$e1 = $_POST['e1'];
$e2 = $_POST['e2'];
$e3= $_POST['e3'];
echo "<h3>Employee Details</h3> ";
echo "Name : ".$_SESSION['eno']."<br>";
echo "Address : ".$_SESSION['enm']."<br>";
echo "Class : ".$_SESSION['eadd']."<br><br>";echo "basic : ".$e1."<br>";
echo "DA : ".$e2."<br>";
echo "HRA : ".$e3."<br>";
$total = $e1+$e2+$e3;
echo "<h2>Total Of Earnings Is : ".$total."</h2>";
?>

5-----
<?xml version="1.0"?>
<iteminfo>
   <item id="101">
     <iname>pen</iname>
      <iprice>15.00</iprice>
     <iqty>20</iqty>
  </item>
 <item id="102">
     <iname>book</iname>
      <iprice>38.00</iprice>
     <iqty>12</iqty>
  </item>
 <item id="103">
     <iname>pencil</iname>
      <iprice>5.00</iprice>
     <iqty>25</iqty>
  </item>
 <item id="104">
     <iname>calculator</iname>
      <iprice>175.00</iprice>
     <iqty>5</iqty>
  </item>
 <item id="105">
     <iname>Scale</iname>
      <iprice>10.00</iprice>
     <iqty>20</iqty>
  </item>
</iteminfo>


6----
<?php
$xml=simplexml_load_file('book.xml') or die("can not load");
echo"BOOK DETAILS<br>";
echo"<table border='1'>";
echo"<tr><th>bid</th><th>bname</th><th>author</th><th>publication</th><th>price</th></tr>";
foreach($xml->Book as $a)
{
echo "<tr>";
echo"<td>".$a['bid']."</td>";
echo "<td>".$a->bname."</td>";
echo "<td>".$a->author."</td>";
echo "<td>".$a->publication."</td>";
echo"<td>".$a->price."</td></tr>";
}
echo"</table>";


?>

This XML file does not appear to have any style information associated with it. The document tree is shown below.
<bookinfo>
<Book bid="b001">
<bname>java</bname>
<author> abc </author>
<publication>Vision</publication>
<price>123</price>
</Book>
<Book bid="b002">
<bname>PHP</bname>
<author> pqr </author>
<publication>Techmax</publication>
<price>250</price>
</Book>
<Book bid="b001">
<bname>OS</bname>
<author> qqq </author>
<publication>Nirali</publication>
<price>127</price>
</Book>
</bookinfo>

7----
<?php
$dom=new DomDocument();
$dom->load("movie.xml");
echo "<b>movies title</b><br>";
$t=$dom->getElementsByTagName("title");
foreach($t as $node)
{
	print $node->textContent;
	echo "<br>";
}
echo "<b>actor name</b><br>";
$t1=$dom->getElementsByTagName("actor");
foreach($t1 as $node)
{
	print $node->textContent;
	echo "<br>";
}
?>

<movieinfo>
<movie no="101">
<title>Sooryavanshi</title>
<actor>akshay kumar</actor>
<ryear>2021</ryear>
</movie>
<movie no="102">
<title>Simba</title>
<actor>Ranbir Singh</actor>
<ryear>2020</ryear>
</movie>
<movie no="103">
<title>Bahubali</title>
<actor>Prabhas</actor>
<ryear>2018</ryear>
</movie>
<movie no="104">
<title>Radhe</title>
<actor>Salman Khan</actor>
<ryear>2020</ryear>
</movie>
</movieinfo>


8----

<html>
<script type="text/javascript">
function disp()
{
  var msg=document.getElementById("t1");
   alert("hello "+msg.value+" exams are near you have to study");
}
function add( )
{
   var a=parseInt(prompt("Enter first number"));
   var b=parseInt(prompt("Enter second number"));
   var c=a+b;
    alert("addition of two numbers are"+c);
}
 
</script>
<body>
<input type=text id="t1"><br>
<input type=submit onclick="disp()" value="alert">
<input type=submit onclick="add()" value="addition">
</body>
</html>

9-----

<html>
<head>
<script type="text/javascript">

function pasuser(form) {
if (form.id.value=="ty") { 
if (form.pass.value=="bcs") {              
alert("welcome Login successful");
} else {
alert("Invalid Password")
}
} else {  alert("Invalid UserID")
}
}

</script>
</head>
<body>
<center>
<form name="login">
Login Area <br>
UserID:<input name="id" type="text"><br><br>
Password:<input name="pass"type="password"><br>
<input type="button" value="Login"onClick="pasuser(this.form)">
<input type="Reset"></form></center></body>

10----

<html>
<head>
 <script src="js/jquery-3.6.0.min.js">  
 </script>   
 <script type="text/javascript" language="javascript">  
$(document).ready(function()
     {
     $("#btn1").click(function(){ 
$("p").before(" <b>before text</b>."); 
});
 $("#btn2").click(function(){ 
$("p").after("<i>after text</i>"); 
});
   
 });
</script>
</head>
<body> 
<p> this is web technology part 2</p><br>
 <button id="btn1">befor </button> 
<button id="btn2">After </button>
 </body>
</html>

11----

<html>
<head>
<script language="javascript">
function change()
{
if(document.frm.txt1.value!="")
{
document.getElementById("txt").style.color="red";
document.getElementById("txt").style.fontSize="18px";
}
else
{
document.getElementById("txt").src='Delete.png';
}
 

}
</script>
</head>
<body>
<form name="frm">
Enter name:<input type="text" name="txt1" id="txt" onmouseover="change()">
<input type="button" name="subm" id="sub1" onclick="change()" value="click">
</form>
</body>
</html>

12----
<?php
                
                $fp = fopen("contact.dat",'r');
                echo "<table border=1>";
    echo "<tr><th>Sr. No.</th><th>Name</th><th>Residence No.</th><th>Mob. no.<th><th>Relation</th></tr>";
             
while($row = fscanf($fp,"%s %s %s %s %s"))
                {
                                echo "<tr>";
                                foreach($row as $r)
                                {
                                                echo "<td>$r</td>";                           
                                }                           
                                echo "</tr>";
                }
                                echo "</table>";
                fclose($fp);
?>

1 bhn 8787 876786786 abc
2 bhb 76576 67687678687 hb
3 ygy 676 7876876 jh


13----
<?php
$a=array("amit","ajay","atul","sanket","sarthak","vedant","harshal","pratham","hardik","rahul","aryan");

$q=$_GET['q'];

if(strlen($q)>0)
{       
         $match="";
		  
         for($i=0;$i<count($a);$i++)
         {
                     if(strtolower($q)==strtolower(substr($a[$i],0,strlen($q))))
                     {
                                 if($match=="")
                                 $match=$a[$i];                         
                                  else 
									$match=$match.",".$a[$i];
                     }          
         }
if($match=="")
echo "hello i don't No you";
else
	echo "hello master ".$match;
}
?>

14----
<?php
if(isset($_GET["n"]))
{
$q=$_GET["n"];
$host = "localhost";
$port = "5432";
$dbname = "postgres";
$user = "postgres";
$password = "pc2002";
$conn = pg_connect("host=$host port=$port dbname=$dbname user=$user password=$password");
if (!$conn)
 {
    die("Connection failed: " . pg_last_error());
}

$sql="SELECT * FROM teacher WHERE tno=$q";
$result=pg_query($conn,$sql);

echo"<table border='1'>";
echo"<tr>";
echo"<th>TNO</th>";
echo"<th>TEACHERNAME</th>";
echo"<th>QUALIFICATION</th>";
echo"<th>TEACHERSALARY</th>";
echo"</tr>";
while ($row = pg_fetch_assoc($result)) {
    echo "<tr>";
    echo "<td>" . $row['tno'] . "</td>";
    echo "<td>" . $row['tname'] . "</td>";
    echo "<td>" . $row['qualification'] . "</td>";
    echo "<td>" . $row['salary'] . "</td>";
    echo "</tr>";
}
echo"</table>";
}
?>

15----
<?php
$a=array("amit","ajay","atul","sanket","sarthak","vedant","harshal","pratham","hardik","rahul","aryan");

$q=$_GET['q'];

if(strlen($q)>0)
{       
         $match="";
		  
         for($i=0;$i<count($a);$i++)
         {
                     if(strtolower($q)==strtolower(substr($a[$i],0,strlen($q))))
                     {
                                 if($match=="")
                                 $match=$a[$i];                         
                                  else 
									$match=$match.",".$a[$i];
                     }          
         }
if($match=="")
echo "no suggestion";
else
	echo $match;
}
?>

16----

<!DOCTYPE html>
<html>
<head>
	<title>Book Details</title>
	<script src="jquery.js"></script>
	<script type="text/javascript">
		$(document).ready(function(){
			$('#bookSelect').change(function(){
				var selectedBook = $(this).val();
				$.ajax({
					type: "GET",
					url: "books.xml",
					dataType: "xml",
					success: function(xml){
						$(xml).find('book').each(function(){
							var title = $(this).find('title').text();
							if(title === selectedBook){
								var author = $(this).find('author').text();
								var year = $(this).find('year').text();
								var price = $(this).find('price').text();
								var details = "Author: " + author + "<br>Year: " + year + "<br>Price: $" + price;
								$('#bookDetails').html(details);
							}
						});
					}
				});
			});
		});
	</script>
</head>
<body>
	<h1>Book Details</h1>
	<select id="bookSelect">
		<option value="">--Select a Book--</option>
		<option value="Harry Potter and the Philosopher's Stone">Harry Potter and the Philosopher's Stone</option>
		<option value="The Hobbit">The Hobbit</option>
		<option value="To Kill a Mockingbird">To Kill a Mockingbird</option>
	</select>
	<div id="bookDetails"></div>
</body>
</html>


<library>
<book>
<title>Harry Potter and the Philosopher's Stone</title>
<author>J.K. Rowling</author>
<year>1997</year>
<price>10.99</price>
</book>
<book>
<title>The Hobbit</title>
<author>J.R.R. Tolkien</author>
<year>1937</year>
<price>8.99</price>
</book>
<book>
<title>To Kill a Mockingbird</title>
<author>Harper Lee</author>
<year>1960</year>
<price>12.99</price>
</book>
</library>

17----

<!DOCTYPE html>
<html>
<head>
	<title>Hello, Good Morning!</title>
</head>
<body onload="showAlert()">
	<script>
		function showAlert() {
			alert("Hello, Good Morning!");
		}
	</script>

	<h2>Student Registration Form</h2>
	<form>
		<label for="name">Name:</label>
		<input type="text" id="name" name="name"><br><br>

		<label for="email">Email:</label>
		<input type="email" id="email" name="email"><br><br>

		<label for="phone">Phone:</label>
		<input type="number" id="phone" name="phone" placeholder="Enter digit"><br><br>

		<label for="address">Address:</label>
		<textarea id="address" name="address"></textarea><br><br>

		<input type="submit" value="Submit">
	</form>
</body>
</html>


18-----

<html>
<head>
<script type=text/javascript>
function disp()
{
  var p,c,next,i;
  n= parseInt(document.getElementById("t1").value);
       p=0;
       c=1;
       next=p+c;
       document.write(p+"  "+c+"  "+next);
       i=3;
   while(i<=n)
           {
            p=c;
           c=next;
           next=p+c;
            document.write(next+"  ");
            i++;
          }
}
	</script>
</head>
<body>
Enter the number of terms you want to print <input type=text id=t1><br>
	<input type=submit value="Print Fibonacci Numbers" onclick="disp()">

</body>
</html>


19----

<!DOCTYPE html>
<html>
<head>
	<title>User Login Form</title>
</head>
<body>
	<h2>User Login Form</h2>
	<form onsubmit="return validateForm()">
		<label for="username">Username:</label>
		<input type="text" id="username" name="username"><br><br>

		<label for="password">Password:</label>
		<input type="password" id="password" name="password"><br><br>

		<input type="submit" value="Submit">
	</form>

	<script>
		function validateForm() {
			var username = document.getElementById("username").value;
			var password = document.getElementById("password").value;

			if (username == "" || password == "") {
				alert("Please enter both username and password");
				return false;
			} else if (username.length < 5) {
				alert("Username must be at least 5 characters long");
				return false;
			} else if (password.length < 8) {
				alert("Password must be at least 8 characters long");
				return false;
			}

			return true;
		}
	</script>
</body>
</html>


20----
<students>
<student>
<id>101</id>
<name>John Doe</name>
<major>Computer Science</major>
<grade>85</grade>
</student>
<student>
<id>102</id>
<name>Jane Smith</name>
<major>Electrical Engineering</major>
<grade>92</grade>
</student>
<student>
<id>103</id>
<name>Bob Johnson</name>
<major>Business Administration</major>
<grade>78</grade>
</student>
<student>
<id>104</id>
<name>Alice Lee</name>
<major>Art History</major>
<grade>91</grade>
</student>
<student>
<id>105</id>
<name>Mark Davis</name>
<major>Physics</major>
<grade>88</grade>
</student>
</students>

24----
<?php
$co=$_POST['t1'];
$xml=simplexml_load_file('stud.xml') or die("can not load");
echo"student details<br>";
echo"<table border='1'>";
echo"<tr><th>sid</th><th>sname</th><th>address</th><th>college</th><th>course</th></tr>";
foreach($xml->stud as $a)
{
   if($a->course==$co)
  {
 
echo "<tr>";
echo"<td>".$a['rno']."</td>";
echo "<td>".$a->name."</td>";
echo "<td>".$a->address."</td>";
echo "<td>".$a->college."</td>";
echo"<td>".$a->course."</td></tr>";
}
}
echo"</table>";

<student>
<stud rno="101">
<name>abc</name>
<address>Nahsik</address>
<college>kkw</college>
<course>bcs</course>
</stud>
<stud rno="102">
<name>pqr</name>
<address>Nahsik</address>
<college>kthm</college>
<course>bba</course>
</stud>
<stud rno="103">
<name>xyz</name>
<address>Nahsik</address>
<college>byk</college>
<course>bca</course>
</stud>
</student>

25----

?>
<?php
// Create a new XML document
$xml = new DOMDocument();
$xml->formatOutput = true;

// Add a root element called "CricketTeam"
$cricketTeamElement = $xml->createElement("CricketTeam");
$xml->appendChild($cricketTeamElement);

// Add a child element called "Team" with country="Australia"
$teamElement = $xml->createElement("Team");
$teamElement->setAttribute("country", "Australia");
$cricketTeamElement->appendChild($teamElement);

// Add child elements for player, runs, and wicket
$playerElement = $xml->createElement("player", "John Smith");
$teamElement->appendChild($playerElement);

$runsElement = $xml->createElement("runs", "100");
$teamElement->appendChild($runsElement);

$wicketElement = $xml->createElement("wicket", "5");
$teamElement->appendChild($wicketElement);

// Add a child element called "Team" with country="India" and add child elements for player, runs, and wicket
$teamElement = $xml->createElement("Team");
$teamElement->setAttribute("country", "India");
$cricketTeamElement->appendChild($teamElement);

$playerElement = $xml->createElement("player", "Rohit Sharma");
$teamElement->appendChild($playerElement);

$runsElement = $xml->createElement("runs", "150");
$teamElement->appendChild($runsElement);

$wicketElement = $xml->createElement("wicket", "0");
$teamElement->appendChild($wicketElement);

// Add another team from India
$teamElement = $xml->createElement("Team");
$teamElement->setAttribute("country", "India");
$cricketTeamElement->appendChild($teamElement);

$playerElement = $xml->createElement("player", "Virat Kohli");
$teamElement->appendChild($playerElement);

$runsElement = $xml->createElement("runs", "50");
$teamElement->appendChild($runsElement);

$wicketElement = $xml->createElement("wicket", "0");
$teamElement->appendChild($wicketElement);

// Save the XML document to a file named "cricket.xml"
$xml->save("cricket.xml");
?>


26----
<?php
if(isset($_GET["n"]))
{
$q=$_GET["n"];
$host = "localhost";
$port = "5432";
$dbname = "postgres";
$user = "postgres";
$password = "pc2002";
$conn = pg_connect("host=$host port=$port dbname=$dbname user=$user password=$password");
if (!$conn)
 {
    die("Connection failed: " . pg_last_error());
}

$sql="SELECT * FROM teacher WHERE tno=$q";
$result=pg_query($conn,$sql);

echo"<table border='1'>";
echo"<tr>";
echo"<th>TNO</th>";
echo"<th>TEACHERNAME</th>";
echo"<th>QUALIFICATION</th>";
echo"<th>TEACHERSALARY</th>";
echo"</tr>";
while ($row = pg_fetch_assoc($result)) {
    echo "<tr>";
    echo "<td>" . $row['tno'] . "</td>";
    echo "<td>" . $row['tname'] . "</td>";
    echo "<td>" . $row['qualification'] . "</td>";
    echo "<td>" . $row['salary'] . "</td>";
    echo "</tr>";
}
echo"</table>";
}
?>

27----
<?php
// Get the form data
$name = $_POST["name"];
$age = $_POST["age"];
$nationality = $_POST["nationality"];

// Validate the data
$errorMsg = "";
if (strtoupper($name) != $name) {
	$errorMsg .= "Name should be in upper case letters only.<br>";
}
if ($age < 18) {
	$errorMsg .= "Age should not be less than 18 years.<br>";
}
if ($nationality != "Indian") {
	$errorMsg .= "Nationality should be Indian.<br>";
}

// Send the response back to the client
if ($errorMsg == "") {
	echo "valid";
} else {
	echo $errorMsg;
}
?>

28----
<?php
// Get the form data
$username = $_POST["username"];
$password = $_POST["password"];

// Connect to the database
$servername = "localhost";
$dbname = "myDB";
$usernameDB = "myUsername";
$passwordDB = "myPassword";
$conn = new mysqli($servername, $usernameDB, $passwordDB, $dbname);
if ($conn->connect_error) {
	die("Connection failed: " . $conn->connect_error);
}

// Query the database for the user's information
$sql = "SELECT * FROM users WHERE username='$username' AND password='$password'";
$result = $conn->query($sql);

// Check if the query returned a row
if ($result->num_rows > 0) {
	echo "valid"; // If the data is valid, return "valid"
} else {
	echo "Invalid username or password."; // If the data is invalid, return an error message
}

// Close the database connection
$conn->close();
?>


29----
<html>
<body>
<form action="<?php echo $_SERVER['PHP_SELF'] ?>" method=POST>
Enter number<input type=text name=t1><br>
select operation<br>
<input type=radio name=r1 value=1>Fibbonaci series<br>
<input type=radio name=r1 value=2>sum of digits<br>
<input type=submit value=ok>
</form>
<?php
$n=$_POST['t1'];
$ch=$_POST['r1'];
if($ch==1)
  {
       $p=0;
       $c=1;
       $next=$p+$c;
       echo  $p."   ".$c."  ".$next." ";
       $i=3;
   while($i<=$n)
           {
            $p=$c;
           $c=$next;
           $next=$p+$c;
            echo $next."  ";
            $i++;
          }

    

  }
else if($ch==2)
  {
  $sum=0;
  while($n!=0)
    {
       $d=$n%10;
       $sum=$sum+$d;
       $n=$n/10;
    }
echo "sum of digits are".$sum;

  }
?>
</body>
</html>


30----
<Bookstore>
<Yoga>
<Book>
<Book_Title>The Yoga Sutras of Patanjali</Book_Title>
<Book_Author>Patanjali</Book_Author>
<Book_Price>10.99</Book_Price>
</Book>
<Book>
<Book_Title>Light on Yoga</Book_Title>
<Book_Author>B.K.S. Iyengar</Book_Author>
<Book_Price>15.99</Book_Price>
</Book>
<Book>
<Book_Title>The Heart of Yoga</Book_Title>
<Book_Author>T.K.V. Desikachar</Book_Author>
<Book_Price>12.99</Book_Price>
</Book>
</Yoga>
<Story>
<Book>
<Book_Title>The Great Gatsby</Book_Title>
<Book_Author>F. Scott Fitzgerald</Book_Author>
<Book_Price>8.99</Book_Price>
</Book>
<Book>
<Book_Title>To Kill a Mockingbird</Book_Title>
<Book_Author>Harper Lee</Book_Author>
<Book_Price>9.99</Book_Price>
</Book>
<Book>
<Book_Title>1984</Book_Title>
<Book_Author>George Orwell</Book_Author>
<Book_Price>7.99</Book_Price>
</Book>
</Story>
<Technical>
<Book>
<Book_Title>Programming PHP</Book_Title>
<Book_Author>Kevin Tatroe, Peter MacIntyre, Rasmus Lerdorf</Book_Author>
<Book_Price>22.99</Book_Price>
</Book>
<Book>
<Book_Title>Head First Design Patterns</Book_Title>
<Book_Author>Eric Freeman, Elisabeth Robson, Bert Bates, Kathy Sierra</Book_Author>
<Book_Price>19.99</Book_Price>
</Book>
<Book>
<Book_Title>Clean Code</Book_Title>
<Book_Author>Robert C. Martin</Book_Author>
<Book_Price>16.99</Book_Price>
</Book>
</Technical>
</Bookstore>
