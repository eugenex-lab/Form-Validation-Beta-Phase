<template >
  <form @submit.prevent="submitForm">
    <div class="form-control">
      <label for="user-name">Your Name</label>
      <input id="user-name" name="user-name" type="text" v-model="userName" />
    </div>
    <div class="form-control">
      <label for="age">Your Age (Years)</label>
      <input id="age" name="age" type="number" v-model="ageInput"/>
    </div>
    <div class="form-control">
      <label for="referrer">Who will you vote for for Presidential election?</label>
      <select id="referrer" name="referrer" v-model="referrerInput">
        <option value="apc">APC</option>
        <option value="pdp">PDP</option>
        <option value="labourParty">Labor Party</option>
      </select>
    </div>
    <div class="form-control">
      <h2>What areas should be the focus of the next regime?</h2>
      <div>
        <input id="interest-news" name="education" type="checkbox"  v-model="interestNews" />
        <label for="interest-news">Education</label>
      </div>
      <div>
        <input id="interest-tutorials" name="roadInfra" type="checkbox"  />
        <label for="interest-tutorials">Road and Infrastructure</label>
      </div>
      <div>
        <input id="interest-nothing" name="fightCorruption" type="checkbox" />
        <label for="interest-nothing">Fight Corruption</label>
      </div>
    </div>
    <div class="form-control">
      <h2>Where do you see your self in 10 years?</h2>
      <div>
        <input id="how-video" name="how" type="radio" />
        <label for="how-video">Video Courses</label>
      </div>
      <div>
        <input id="how-blogs" name="how" type="radio" />
        <label for="how-blogs">Blogs</label>
      </div>
      <div>
        <input id="how-other" name="how" type="radio" />
        <label for="how-other">Other</label>
      </div>
    </div>
    <div>
      <button
      @submit="submitForm"
      >Save Data</button>
    </div>
  </form>
</template>

<script>

export default {
  data() {
    return {
      userName: 'wwww',
      userAge:   null,
      referrerInput: 'apc'

    };
  },

  methods:{
    submitForm(){
      console.log(" was pressed");
      console.log("Name:    " + this.userName );
      console.log("Age: " + this.userAge);
      console.log(this.$refs.userAge.value + 5 );
      console.log("Referred: -->>> " + this.referrerInput);


      this.userAge= null;
      this.userName = "";
      this.referrerInput= "apc";



    }
  },
}


</script>
<style scoped>
form {
  margin: 2rem auto;
  max-width: 40rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 2rem;
  background-color: #0cfd7d;
}

.form-control {
  margin: 0.5rem 0;
}

label {
  font-weight: bold;
}

h2 {
  font-size: 1rem;
  margin: 0.5rem 0;
}

input,
select {
  display: block;
  width: 100%;
  font: inherit;
  margin-top: 0.5rem;
}

select {
  width: auto;
}

input[type='checkbox'],
input[type='radio'] {
  display: inline-block;
  width: auto;
  margin-right: 1rem;
}

input[type='checkbox'] + label,
input[type='radio'] + label {
  font-weight: normal;
}

button {
  font: inherit;
  border: 1px solid #0076bb;
  background-color: #0076bb;
  color: white;
  cursor: pointer;
  padding: 0.75rem 2rem;
  border-radius: 30px;
}

button:hover,
button:active {
  border-color: #002350;
  background-color: #002350;
}
</style>