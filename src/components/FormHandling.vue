<template>
  <pre>
    {{ JSON.stringify(formData, null, 2) }}
  </pre>
  <!-- using prevent modifier -->
  <form @submit.prevent="submit">
    <div>
      <label for="name">Name</label>
      <!-- using lazy modifier this will update data when user navigate another -->
      <input type="text" name="" id="name" v-model.lazy="formData.name" />
    </div>
    <div>
      <label for="profile-summary">Profile Summary</label>
      <!-- using space trim modifier -->
      <textarea
        v-model.trim="formData.profileSummary"
        name=""
        id="profile-summary"
        cols="30"
        rows="10"
      ></textarea>
    </div>
    <div>
      <select v-model="formData.country" name="" id="country">
        <option value="myanmar">Myanmar</option>
        <option value="thai">Thai</option>
        <option value="singapore">singapore</option>
        <option value="japan">Japan</option>
      </select>
    </div>
    <div>
      <select multiple v-model="formData.jobLocation" name="" id="country">
        <option value="myanmar">Myanmar</option>
        <option value="thai">Thai</option>
        <option value="singapore">singapore</option>
        <option value="japan">Japan</option>
      </select>
    </div>
    <div>
      <label for="remote">Remote Open?</label>
      <input
        type="checkbox"
        name=""
        id="remote"
        v-model="formData.remoteWork"
      />
    </div>
    <div>
      <label for="html">HTML</label>
      <input
        type="checkbox"
        name=""
        id="html"
        value="html"
        v-model="formData.skillSet"
      />
      <label for="css">CSS</label>
      <input
        type="checkbox"
        name=""
        id="css"
        value="css"
        v-model="formData.skillSet"
      />
      <label for="js">JS</label>
      <input
        type="checkbox"
        name=""
        id="js"
        value="js"
        v-model="formData.skillSet"
      />
      <label for="react">React</label>
      <input
        type="checkbox"
        name=""
        id="react"
        value="react"
        v-model="formData.skillSet"
      />
    </div>
    <div>
      <label for="0-2">0-2</label>
      <input
        type="radio"
        name=""
        id="0-2"
        value="0-2"
        v-model="formData.yearOfExperience"
      />
      <label for="3-5">3-5</label>
      <input
        type="radio"
        name=""
        id="3-5"
        value="3-5"
        v-model="formData.yearOfExperience"
      />
      <label for="5-7">5-7</label>
      <input
        type="radio"
        name=""
        id="5-7"
        value="5-7"
        v-model="formData.yearOfExperience"
      />
    </div>
    <button type="submit">Submit</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      formData: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: false,
        skillSet: [],
        yearOfExperience: "",
      },
    };
  },
  methods: {
    submit(e) {
      e.preventDefault();
      console.log(this.formData);
    },
  },
};
</script>

<style>
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}

input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}

input[type="text"],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}
</style>
