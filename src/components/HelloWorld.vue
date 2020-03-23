<template>
  <div class="hello">
    <h1>Create Your account for free</h1>

    <div class="col-12 row">
      <div class="col-5 text-center regBox">
        <form action="" method="post" enctype="multipart/form-data">
          <div class="form-group text-left row">
            <label for="fullName" class="col-3" style="margin-top:5px;"
              >Full name:</label
            >
            <input
              type="text"
              class="form-control col-8"
              placeholder="Name..."
              required=""
              name="fullName"
            />
          </div>

          <div class="form-group text-left row">
            <label for="Email" class="col-3" style="margin-top:5px;"
              >Email:</label
            >
            <input
              type="email"
              class="form-control col-8"
              placeholder="Email..."
              required=""
              name="Email"
            />
          </div>

          <div class="form-group text-left row">
            <label for="Password" class="col-3" style="margin-top:5px;"
              >Password:</label
            >
            <input
              v-model="pass1"
              type="password"
              class="form-control col-8"
              placeholder="Password..."
              required=""
              name="Password"
            />
          </div>

          <div class="form-group text-left row">
            <label for="confirmPassword" class="col-3" style="margin-top:5px;"
              >Confirm Password:</label
            >
            <input
              v-model="pass2"
              type="password"
              class="form-control col-8"
              placeholder="Confirm Password..."
              required=""
              name="confirmPassword"
            />

            <label
              v-if="pass1 !== pass2"
              for="Email"
              class="col-6 alert-danger"
              style="margin-top:5px; margin-left:25%; color:red;"
              >{{ passMsg }}</label
            >
          </div>
          <!-- :disabled="isDisabled" -->
          <div class="form-group">
            <input
              class="btn btn-primary "
              type="submit"
              name="register"
              value="Register"
            />
          </div>
        </form>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      pass1: "",
      pass2: "",
      passMsg: "Password dosenot match",
    };
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
