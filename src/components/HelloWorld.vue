<template>
  <div class="hello">
    <h1>Create Your account for free</h1>

    <div class="col-12 row">
      <div class="col-lg-5 col-md-6 col-sm-12 text-center regBox">
        <form action="" method="post" enctype="multipart/form-data">
          <div class="form-group text-left row">
            <label
              for="fullName"
              class="col-lg-3 col-md-4 col-sm-11"
              style="margin-top:5px;"
              >Full name:</label
            >
            <input
              type="text"
              class="form-control col-lg-8 col-md-7 col-sm-11"
              placeholder="Name..."
              required=""
              name="fullName"
              v-model="userName"
            />
          </div>

          <div class="form-group text-left row">
            <label
              for="Email"
              class="col-lg-3 col-md-4 col-sm-11"
              style="margin-top:5px;"
              >Email:</label
            >
            <input
              type="email"
              class="form-control col-lg-8 col-md-7 col-sm-11"
              placeholder="Email..."
              required=""
              name="Email"
            />
          </div>

          <div class="form-group text-left row">
            <label
              for="Password"
              class="col-lg-3 col-md-4 col-sm-11"
              style="margin-top:5px;"
              >Password:</label
            >
            <input
              v-model="pass1"
              type="password"
              class="form-control col-lg-8 col-md-7 col-sm-11"
              placeholder="Password..."
              required=""
              name="Password"
            />
          </div>

          <div class="form-group text-left row">
            <label
              for="confirmPassword"
              class="col-lg-3 col-md-4 col-sm-11"
              style="margin-top:5px;"
              >Confirm Password:</label
            >
            <input
              v-model="pass2"
              type="password"
              class="form-control col-lg-8 col-md-7 col-sm-11"
              placeholder="Confirm Password..."
              required=""
              name="confirmPassword"
            />

            <label
              v-if="pass1 !== pass2"
              for="Email"
              class="col-6 alert-danger"
              style="margin-top:5px; margin-left:25%; color:red;"
              >{{ passNotMatch }}</label
            >

            <label
              v-if="pass1 == pass2 && pass1.length < 8"
              for="Email"
              class="col-6 alert-danger"
              style="margin-top:5px; margin-left:25%; color:red;"
              >{{ passLessThan8 }}</label
            >

          </div>
          <!-- :disabled="isDisabled" -->
          <div class="form-group">
            <label for="terms">
              <input
                id="terms"
                type="checkbox"
                v-model="terms"
                :checked="terms"
              />
              I accept terms
            </label>
            <br />

           <router-link to="/sheet"> <input
              :disabled="isDisabled"
              class="btn btn-primary "
              type="submit"
              name="register"
              value="Register"
            /></router-link>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
const STORAGE_KEY = "user_name";
export default {
  data: function() {
    return {
      pass1: "",
      pass2: "",
      terms: false,
      userName: "",
      passNotMatch: "Password dose not match",
      passLessThan8: 'Password Must be more than 8'
    };
  },

  computed: {
    isDisabled: function() {
      return !this.terms;
    }
  },

  watch: {
    userName: function() {
      return localStorage.setItem(STORAGE_KEY, String(this.userName));
    },

    terms: function() {

      
      if (this.pass2 == this.pass1 && this.pass1.length >= 8) {
        return (this.terms = true);
      } else {
        return (this.terms = false);
      }
    },

    pass1: function() {
      if (this.pass2 == this.pass1 && this.pass1.length >= 8) {
        return (this.terms = true);
      } else {
        return (this.terms = false);
      }
    },

    pass2: function() {
     if (this.pass2 == this.pass1 && this.pass1.length >= 8) {
        return (this.terms = true);
      } else {
        return (this.terms = false);
      }
    }
  },

  name: "HelloWorld"
};
</script>

<style lang="scss" scoped>
.regBox {
  padding: 7px;
  padding-top: 20px !important;
  margin: auto;
  padding: 10px;
  background-color: rgba(250, 250, 245, 0.719) !important;
  box-shadow: 4px 4px 4px 0px rgba(240, 240, 240, 0.719);
}
</style>
