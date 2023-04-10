<template>
  <div class="tweet">
    <div class="thead">
      <div class="account">
        <img class="pfp" src="" alt="profile picture">
        <div class="accat">
          <h3 class="name">Account</h3>
          <h3 class="arroba">@Account</h3>
        </div>
      </div>
      <div>
        <img src="" alt="TweeterLogo">
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
    width: 30%;
    align-items: center;
    border:solid;
    border-color: rgba(128, 128, 128, 0.3);
    border-radius: 2rem;
    padding: 5px; 
  }

  .thead {
    display: flex;
    flex-direction: row;
    justify-content: space-around;
  }

  .tbody {
    width: 100%;
    padding: 5px 15px;
    display: flex;
    align-items: center;
    flex-direction: column;
  }

  .account {
    display: flex;
    flex-direction: row;
  }

  .accat {
    display: flex;
    flex-direction: column;
  }

  .message {
    margin: 10px 0px;
    width: 95%;
    text-align: justify;
    font-size: 1.5rem;
  }

  .date {
    margin: 10px 0px;
    width: 95%;
    text-align: justify;
  }

  .tfooter {
    width: 100%;
    display: flex;
    align-items: center;
    margin-bottom: 20px ;
  }

  #guess {
    width: 95%;
    margin: auto;
    align-items: center;
    border-radius: 10px;
    padding: 0px 5px;
  }

</style>