# Sales-queen-task3
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Dashboard</title>
    <script src="https://kit.fontawesome.com/4f5858a434.js" crossorigin="anonymous"></script>
</head>
<body>
    <div id="header"> 
        <div class="container">
           <nav class="menu">
                <ul id="myMenu">
                   
                    <br>
                    <br>
                    <br>
                    <input type="text" id="mySearch" placeholder="Search.." title="Type in a category">
                    <li><a href="#header">Home</a></li>
                    <li><a href="#tabel">Data Table</a></li>
                    <li><a href="#wrapper">To-Do list</a></li>  
                    <label for="options">Settings</label>
                    <select name="options" id="options">
                      <option value="Data">Data</option>
                      <option value="Network">Network</option>
                      <option value="Account">Account</option>
                      <option value="Log-Out">Log-Out</option>
                    </select>
                    <li><a href="#contact">Contact</a></li>
                    <i class="fa-solid fa-xmark" onclick="closemenu()"></i>
                </ul>
                <i class="fa-solid fa-bars" onclick="openmenu()"></i>      
            </nav>          
        </div>         
    </div>
<!--------------------------------------------------------------------------------------------------------->
   <div id="cards">
      <div class="container">
        <h1><span><b>Sales Queen Dashboard</b></span></h1>
        <div class="card-list">
          <div class="card 1" >
              <h5>Task 1</h5>
              <h6 >Snake Game</h6>
              <p > Use arrow keys or tap on screen to control the snake. Hold down forward to increase speed or backwards to decrease speed. Eat to gain score.</p>
          </div>
          <div class="card 2" >
            <h5>Task 2</h5>
            <h6>Portfolio Website</h6>
            <p>The most practical and memorable ways to share your work with press, potential collaborators or employers. </p>
          </div>
          <div class="card 3" >
              <h5>Task 3</h5>
              <h6>JDBC Connectivity</h6>
              <p>The JDBC API consists of a set of interfaces and classes written in the Java programming language.</p>
          </div>
        </div>
      </div>
    </div>
<!------------------------------------------------------------------------------------------------------------------>
<div id="progress">
  <div class="container">
    <div class="row">
      <div class="progress-col-1">
        <div class="progress-col-1__fill"></div>
        <span class="progress-col-1__text">25%</span>
      </div>
      <div class="progress-col-2">
        <div class="progress-col-2__fill"></div>
        <span class="progress-col-2__text">55%</span>
      </div>
      <div class="progress-col-3">
        <div class="progress-col-3__fill"></div>
        <span class="progress-col-3__text">75%</span>
      </div>
    </div>
  </div>
</div>
<!------------------------------------------------------------------------------------------------------------------------------->
<br>
<br>
<div id="tabel">
<h1><span><b>Projects</b></h1>
<table>
  <tr bgcolor="#fe6afe" >
    <th><b><i>Company</i></b></th>
    <th><b><i>Project</i></b></th>
    <th><b><i>Status</i></b></th>
  </tr>
  <tr>
    <td>Accenture</td>
    <td>Project Velocity</td>
    <td>Yet to complete</td>
  </tr>
  <tr>
    <td>Virtusa</td>
    <td>Runtime Terror</td>
    <td>On going</td>
  </tr>
  <tr>
    <td>Cognizant</td>
    <td>AI tool</td>
    <td>Analizing</td>
  </tr>
  <tr>
    <td>ZOHO</td>
    <td>Smart Guidance</td>
    <td>Completed</td>
  </tr>
  <tr>
    <td>Wipro</td>
    <td>Personal Portfolio</td>
    <td>Yet to complete</td>
  </tr>
  <tr>
    <td>Cloud IQ</td>
    <td>Cloud Computing</td>
    <td>completed</td>
  </tr>
  <tr>
    <td>Mitra Soft</td>
    <td>JDBC connectivity</td>
    <td>Initiating the process</td>
  </tr>
  <tr>
    <td>Prophpenix</td>
    <td>Dot Net</td>
    <td>completed</td>
  </tr>
  <tr>
    <td>Byjus</td>
    <td>Snake Game</td>
    <td>Pending</td>
  </tr>
  <tr>
    <td>NTT Data</td>
    <td>Hospital Website</td>
    <td>Ongoing</td>
  </tr>
  <tr>
    <td>Free Space</td>
    <td>Network</td>
    <td>completed</td>
  </tr>
  <tr>
    <td>Ford</td>
    <td>EV design</td>
    <td>Processing</td>
  </tr>
</table>
</div>
<br>
<br>
<br>
<br>
<!----------------------------------------------------------------------------------------------------------->
<h1><b>Things To Do</b></h1>
<div id="wrapper">
  <h2>Todo List</h2>
  <input type="text" id="input">
  <button id="add">Add</button>
  <div id="todoList">

  </div>
</div>
<script src="app.js"></script>
<!------------------------------------------------------------------------------------------------------------>
<div id="contact">
  <div class="container">
      <div class="row">
          <div class="contact-left">
              <h1 class="sub-title">Contact Me</h1>
              <p><i class="fas fa fa-paper-plane"></i><span>sowndarya09032002@gmail.com</span></p>
              <p><i class="fa-solid fa-phone-volume"></i><span>9361449813</span></p>
             <div class="social-icons">
               <a href="https://instagram.com/_sowndhu_2002_?igshid=NGExMmI2YTkyZg=="><i class="fa-brands fa-instagram"></i></a>
               <a href="https://www.linkedin.com/in/sowndarya-krishnan-ab23731b1"><i class="fa-brands fa-linkedin"></i></a>
               <a href="https://github.com/Sowndarya-Krishnan"><i class="fa-brands fa-square-github"></i></a>
              </div>
            </div>
        </div>
    </div>
  </div>
<!------------------------------------------------------------------------------------------------------------>
<script>
let button = document.getElementById('add')
let todoList = document.getElementById('todoList')
let input = document.getElementById('input');
//local storage,cookies
let todos = [];
window.onload = ()=>{
    todos = JSON.parse(localStorage.getItem('todos')) || []
    todos.forEach(todo=>addtodo(todo))
}

button.addEventListener('click',()=>{
    todos.push(input.value)
    localStorage.setItem('todos',JSON.stringify(todos))
    addtodo(input.value)
    input.value=''
})

function addtodo(todo){
    let para = document.createElement('p');
    para.innerText = todo;
    todoList.appendChild(para)
    
    para.addEventListener('click',()=>{
        para.style.textDecoration = 'line-through'
        remove(todo)
    })
    para.addEventListener('dblclick',()=>{
        todoList.removeChild(para)
        remove(todo)
    })
}

function remove(todo){
    let index = todos.indexOf(todo)
    if (index > -1) {
        todos.splice(index, 1);
      }
    localStorage.setItem('todos',JSON.stringify(todos))
}
</script>
<script>
        var myMenu = document.getElementById("myMenu");

        function openmenu(){
            myMenu.style.left = "0";
        }
        function closemenu(){
            myMenu.style.left = "-200px";
        }
   </script>
</body>
</html>
-------------------------------------- css------------------------------------------------------
body {
    background: #2b2929;
    color: #fff;
}
input{
    margin: 5px;
}
label{
    width: 170px;
    height: 3px;
    border-radius: 5px;
    font-size: 18px;
    padding: 10px;
    margin-left: 15px;
    color: white;

}
label:hover {
    background-color:#fe6afe ;
  }
#mySearch {
    width: 170px;
    height: 5px;
    border-radius: 5px;
    font-size: 18px;
    padding: 10px;
    border: 1px solid #ddd;
  }
  
  /* Style the navigation menu */
  #myMenu {
    list-style-type: none;
    padding: 0;
    margin: 0;
  }
  
  /* Style the navigation links */
  #myMenu li a {
    padding: 3px;
    text-decoration: none;
    color: white;
    display: block;
  }
  
  #myMenu li a:hover {
    background-color:#fe6afe ;
  }
  nav .fa-solid{
    display: block;
    font-size: 25px;
}
nav ul{
    background: grey;
    position: fixed;
    top: 0;
    right: -200px;
    width: 200px;
    height: 100vh;
    padding-top: 50px;
    z-index: 2;
    transition: right 0.5s;
}
nav ul li{
    display: block;
    margin: 25px;
}
nav ul .fa-solid{
    position:absolute;
    top: 25px;
    right: 25px;
    cursor: pointer;
}
/*------------------------------------------------------------------------------*/
h5{
    margin-top: 3px;
    font-size: 30px;
}
h6{
    margin-top: -10px;
    font-size: 20px;
}
p{
    font-size: 18px;
}
#cards{
    padding: 30px 20px;
}
h1{
    text-align: center;
    padding: 5px;
    font-style: italic;
    text-decoration: dotted;
}
h1 span{
    color: #fe6afe;
}
.card-list{
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(250px,1fr));
    grid-gap: 40px;
    margin-top: 10px;
}
.card-list div{
    background: grey;
    padding: 40px;
    font-size: 13px;
    font-weight: 300;
    border-radius: 10px;
    transition: background 0.5s,transform 0.5s;
}
/*---------------------------------------------------------------------------------------------------------*/
#progress{
   border-radius: 10px;
}
.row{
    display: flex;
    justify-content: space-between;
    flex-wrap: wrap;
}
.progress-col-1{
    width: 29%;
    height: 20px;
    margin-left: 25px;
    margin-top: -65px;
    border-radius: 5px;
    background: rgb(61, 62, 61);
}
.progress-col-1__fill{
    width: 25%;
    height: 100%;
    background: #fe6afe;
}
.progress-col-1__text{
    position: absolute;
    top: 85.5%;
    left: 37px;
    transform: translateY(-50%);
    color: white;
}
.progress-col-2{
    width: 29%;
    height: 20px;
    margin-top: -65px;
    margin-right: 422px;
    background: rgb(62, 61, 62);
    border-radius: 5px;
}
.progress-col-2__fill{
    width: 55%;
    height: 100%;
    background: #fe6afe;
}
.progress-col-2__text{
    position: absolute;
    top: 85.5%;
    left: 36%;
    transform: translateY(-50%);
    color: white;
}
.progress-col-3{
    width: 29%;
    height: 20px;
    margin-top: -65px;
    margin-left: 820px;
    background: rgb(60, 61, 60);
    border-radius: 5px;
}
.progress-col-3__fill{
    width: 75%;
    height: 100%;
    background: #fe6afe;
}
.progress-col-3__text{
    position: absolute;
    top: 85.5%;
    left: 840px;
    transform: translateY(-50%);
    color: white;
}
/*--------------------------------------------------------------------------------------------------------*/
table {
    margin-left: 30px;
    font-family:Georgia, 'Times New Roman', Times, serif;
    border-collapse: collapse;
    width: 95%;
    text-align: center;
    border-radius: 5px;
  }
  h1 span{
    color: #fe6afe;
  }
  td, th {
    border: 1px solid white;
    text-align: center;
    padding: 8px;
  }
  
  /*tr:nth-child(even) {
    background-color: rgb(214, 202, 202);
  }
/*--------------------------------------------------------------------------------------------------------*/
#wrapper{
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background-color:#fe6afe;
 }
 h1{
    text-align: center;
    color: #fe6afe;
 }
 #wrapper h2{
     display:flex;
     justify-content: center;
     
 }
 h2{
     color:#fe6afe;
     letter-spacing: 1px;
 }
 input{
     border-radius: 5px;
     border: 2px solid black ;
     margin-top:30px;
     height:2.5em;
     width:250px;
     padding-left:10px;
 }
 input:active{
     border:none;
 }
 #wrapper{
     height:500px;
     width:400px;
     margin:50px auto;
     background-color:#1f2029;
     border-radius:10px;
     padding:30px;
 }
 
 button{
     margin-top:20px;
     background-color:#fe6afe;
     border-radius: 4px;
     height: 44px;
     font-weight: 600;
     padding: 0 30px;
     letter-spacing: 1px;
     border: none;
     color: #102770;
 }
 
 button:hover{
     cursor:pointer;
 }
 #todoList{
     color:white;
     font-size:28px;  
     margin-top:10px; 
 }
 
 #todoList p{
   margin:10px 0px;
 }
 
 #todoList p:hover{
   cursor: pointer;
 }
 /*------------------------------------------------------------------------------------------*/
 .contact-left{
    flex-basis: 35%;
}
.contact-left h1{
    margin-left: -200px;
}
.contact-left p{
    margin-top:30px;
}
.contact-left p i{
    color: #fe6afe;
    margin-left: 25px;
    font-size: 25px;
}
.contact-left span{
    margin-left: 15px ;
}
.social-icons{
    margin-top: 30px;
}
.social-icons a{
    text-decoration: none;
    font-size: 30px;
    margin-left: 20px;
    color:#abababe2 ;
    display: inline-block;
    transition: trasform(0.5s);
}
.social-icons a:hover{
    color: #fe6afe;
    transform: translateY(-5px);
}
/*#progress{
    width: 36%;
    height: 15px;
    background: red;
}
.progress{
    width: 50%;
    height: 20px;
    background: rgb(185, 173, 173);
    border-radius: 5px;
    overflow: hidden;
}
.progress__fill{
    width: 25%;
    height: 100%;
    background: red;
}
.progress__text{
    position: absolute;
    top: 37%;
    left: 30px;
    transform: translateY(-50%);
    color: black;
}
