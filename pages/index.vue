<template>
  <div
    class="container relative w-full bg-white min-h-screen overflow-hidden"
    :class="{ 'sign-up-mode': signUpMode }"
  >
    <div class="forms-container absolute w-full h-full top-0 left-0">
      <div
        class="signin-signup absolute top-1/2 left-3/4 transform -translate-x-1/2 -translate-y-1/2 w-1/2 transition duration-1000 ease-in-out grid grid-cols-1 z-5"
      >
        <form
          @submit.prevent="submitLogin"
          class="sign-in-form flex items-center justify-center flex-col p-0 5rem transition-all duration-200 ease-in-out overflow-hidden col-span-1 row-span-1"
        >
          <h2 class="title">Sign in</h2>
          <div class="input-field flex items-center">
            <i class="fas fa-user mr-2"></i>
            <input
              type="text"
              v-model="username"
              placeholder="Username"
              class="input-field"
            />
          </div>
          <div class="input-field flex items-center">
            <i class="fas fa-lock mr-2"></i>
            <input
              type="password"
              v-model="password"
              placeholder="Password"
              class="input-field"
            />
          </div>
          <input type="submit" value="Login" class="btn solid" />
          <p class="social-text">Or Sign in with social platforms</p>
          <div class="social-media flex">
            <a href="#" class="social-icon">
              <i class="fab fa-facebook-f"></i>
            </a>
            <a href="#" class="social-icon">
              <i class="fab fa-twitter"></i>
            </a>
            <a href="#" class="social-icon">
              <i class="fab fa-google"></i>
            </a>
            <a href="#" class="social-icon">
              <i class="fab fa-linkedin-in"></i>
            </a>
          </div>
        </form>

        <form @submit.prevent="submitSignup" class="sign-up-form">
          <h2 class="title">Sign up</h2>
          <div class="input-field flex items-center">
            <i class="fas fa-user mr-2"></i>
            <input
              type="text"
              v-model="username"
              placeholder="Username"
              class="input-field"
            />
          </div>
          <div class="input-field flex items-center">
            <i class="fas fa-envelope mr-2"></i>
            <input
              type="email"
              v-model="email"
              placeholder="Email"
              class="input-field"
            />
          </div>
          <div class="input-field flex items-center">
            <i class="fas fa-lock mr-2"></i>
            <input
              type="password"
              v-model="password"
              placeholder="Password"
              class="input-field"
            />
          </div>
          <input type="submit" class="btn" value="Sign up" />
          <p class="social-text">Or Sign up with social platforms</p>
          <div class="social-media flex">
            <a href="#" class="social-icon">
              <i class="fab fa-facebook-f"></i>
            </a>
            <a href="#" class="social-icon">
              <i class="fab fa-twitter"></i>
            </a>
            <a href="#" class="social-icon">
              <i class="fab fa-google"></i>
            </a>
            <a href="#" class="social-icon">
              <i class="fab fa-linkedin-in"></i>
            </a>
          </div>
        </form>
      </div>
    </div>

    <div class="panels-container">
      <div class="panel left-panel flex flex-col items-center justify-around">
        <div class="content text-center">
          <h3>New here ?</h3>
          <p>
            Lorem ipsum, dolor sit amet consectetur adipisicing elit. Debitis,
            ex ratione. Aliquid!
          </p>
          <button class="btn transparent" ref="signUpBtn">Sign up</button>
        </div>
        <img src="./assets/img/log.svg" class="image" alt="" />
      </div>
      <div class="panel right-panel flex flex-col items-center justify-around">
        <div class="content text-center">
          <h3>One of us ?</h3>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Nostrum
            laboriosam ad deleniti.
          </p>
          <button class="btn transparent" ref="signInBtn">Sign in</button>
        </div>
        <img src="./assets/img/register.svg" class="image" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      signUpMode: false,
    };
  },
  mounted() {
    const signInBtn = this.$refs.signInBtn;
    const signUpBtn = this.$refs.signUpBtn;

    signInBtn.addEventListener("click", this.handleSignInClick);
    signUpBtn.addEventListener("click", this.handleSignUpClick);
  },
  methods: {
    handleSignInClick() {
      this.signUpMode = false;
    },
    handleSignUpClick() {
      this.signUpMode = true;
    },
  },
};
</script>
