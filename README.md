# 3-hours-Project-on-Javascript
Making an Expense tracker app with local storage integration
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>3 hours Project on Javascript</title>
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    Making an Expense tracker app with local storage integration
    <header>
      <form onsubmit="saveToLocalStorage(event)">

    </header>

    <section class="container">
      <form id="my-form">
        <h1>chooseexpenseinfromation</h1>
        <div class="msg"></div>
        <div>
          <label for="chooseexpenseamount:">chooseexpenseamount::</label>
          <input type="text" id="chooseexpenseamount:">
        </div>
        <div>
          <label for="choosedescription:">choosedescription:</label>
          <input type="text" id="choosedescription:">
        </div>
        
        
        <form action="#">
            <label for="lang">choose a category:</label>
            <select name="choose a category:" id="ex">
              <option value="food">food</option>
              <option value="movie">movie</option>
              <option value="dinner">dineer</option>
              <option value="game">game</option>
              
            </select>
            <div>
            <input type="submit" value="Add expense" />
        </div>
      </form>
      </form>
    </form>



    </section>


    <script>
    let Name = document.getElementById('chooseexpenseamount:">');
let Email = document.getElementById('choosedescription:');
let Button = document.getElementById('Add expense');
let list = document.getElementById('choose a category:');
Button.addEventListener('click', (event)=>{
    event.preventDefault();
    let chooseexpenseamount:"> = chooseexpenseamount:">.value
    let choosedescription: = choosedescription:.value;
    
    
    let myObj = {
        chooseexpenseamount:">,
        choosedescription:
    }
   let myObj_serialized = localStorage.setItem(myObj.email, JSON.stringify(myObj));
   console.log(myObj_serialized);
   displayUser(myObj);

   chooseexpenseamount:">.value = ''
   choosedescription:.value = ''
})

window.addEventListener('DOMContentLoaded', (e) =>{
   
    Object.keys(localStorage).forEach((key) => {
        let user = JSON.parse(localStorage.getItem(key))
        displayUser(user);
    })
})

function displayUser(user) {
    let parentNode = document.getElementById('choose a category:');

    parentNode.innerHTML = parentNode.innerHTML + `<li id='${user.email}'>${user.chooseexpenseamount:">} : ${user.choosedescription:}
                                                   <button onClick=deleteUser('${user.choosedescription:}')>Delete</button>
                                                   <button onClick=editUser('${user.choosedescription:}','${user.chooseexpenseamount:">}')>Edit</button></li>`
}

function deleteUser(chooseexpenseamount:">) {
    localStorage.removeItem(userId)
    removeListOnScreen(userId)
}

function removeListOnScreen(email) {
    let parentNode = document.getElementById('choose a category:');
    let element = document.getElementById(choosedescription:);
    parentNode.removeChild(element);
}
function editUser(userId){
     document.getElementById('chooseexpenseamount:">').value = 'userId';
     document.getElementById('choosedescription:').value = 'choosedescription:';
    
     deleteUser(userId)
    
}
      function saveToLocalStorage(event) {
        event.preventDefault();
        const chooseexpenseamount: = event.target.chooseexpenseamount:.value;
        const email = event.target.choosedescription:.value;
        const tell = event.target.choose a category:.value;
        localStorage.setItem('chooseexpenseamount:', chooseexpenseamount:);
           localStorage.setItem('choosedescription:', choosedescription:);
           localStorage.setItem('choose a category:', choose a category:);

     const obj ={
        chooseexpenseamount:,
      choosedescription:,
       choose a category:
      }
      localStorage.SetItem(obj.choosedescription:, JSON.stringify(obj));

      function shownameonScreen(obj){
        const parentElem = document.getElementById('my-form')

    parentElem.innerHTML = parentElem.innerHTML +  <li> $( obj.chooseexpenseamount: ) - $( obj.choosedescription: )- $(obj.choose a category:) </li>
     }
  }
    </script>
  </body>
</html>
