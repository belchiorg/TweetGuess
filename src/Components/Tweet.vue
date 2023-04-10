<template>
  <div class="tweet">
    <div class="thead">
      <div class="account">
        <img class="pfp" src="https://companieslogo.com/img/orig/GOOG-0ed88f7c.png?t=1633218227" alt="profile picture">
        <div class="accat">
          <h3 class="name">Account</h3>
          <h3 class="arroba">@Account</h3>
        </div>
      </div>
      <div>
        <img class="TwitterLogo" src="https://www.iconpacks.net/icons/2/free-twitter-logo-icon-2429-thumb.png" alt="TweeterLogo">
      </div>
    </div>
    <div class="tbody">
      <p class="message">Eu sou bue curtido, teste de um texto muito maior, ver o que acontece com isto </p>
      <p class="date">2:57 PM | Mar 15, 2023</p>
    </div>
    <hr>
    <div class="tfooter">
      <input type="text" name="Guess" id="guess">
    </div>
  </div>
</template>

<style scoped>
  .tweet {
    display: flex;
    flex-direction: column;
    margin: auto;
    width: 50%;
    max-width: 700px;
    align-items: center;
    border:solid;
    border-color: rgba(128, 128, 128, 0.3);
    border-radius: 2rem;
    padding: 5px 0px; 
  }

  .thead {
    display: flex;
    flex-direction: row;
    width: 95%;
    justify-content: space-between;
  }

  .tbody {
    width: 100%;
    padding: 3px 15px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .account {
    display: flex;
    flex-direction: row;
    width: fit-content;
    align-items: center;
  }

  .accat {
    display: flex;
    flex-direction: column;
  }

  .message {
    margin: 0px 0px;
    width: 95%;
    line-height: normal;
    text-align: justify;
    font-size: 1.5rem;
  }


  h3, .date {
    font-size: 1rem;
  }

  .name {
    font-weight: bold;
  }

  .date, .arroba {
    color: rgb(70, 70, 70);
  }

  .date {
    margin: 5px 0px 5px 0px;
    width: 95%;
    text-align: justify;
  }

  hr {
    width: 90.25%;
    height: 2px;
    border-color: rgba(128, 128, 128, 0.3);
  }

  .tfooter {
    width: 95%;
    display: flex;
    align-items: center;
    margin-top: 15px;
    margin-bottom: 15px ;
  }

  #guess {
    width: 95%;
    margin: auto;
    align-items: center;
    border-radius: 10px;
    padding: 0px 10px;
    font-size: 1.4rem;
  }

  .thead img {
    border-radius: 100%;
    height: 50px;
    width: 50px;
    margin: 5px 15px;
  }

</style>