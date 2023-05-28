<template>
  <div class="container mt-4" id="app">
    <form @submit.prevent="registerUser" novalidate>
      <div class="row">
        <div class="col-sm-5 mx-auto">


          <button @click="backStep" type="button" class="btn btn-light col-sm-5 mr-1">Вход</button>
          <button @click="nextStep" type="button" class="btn btn-light col-sm-6">Регистрация</button>


          <div v-show="step === 1" class="step">
            <div class="mb-5 mt-5">
              <input type="email" class="form-control" id="email" aria-describedby="emailHelp" placeholder="Ваша почта">
            </div>

            <div class="mb-5">
              <input type="password" class="form-control" id="pass" placeholder="Пароль">
            </div>

            <div class="mb-3 form-check">
              <input type="checkbox" class="form-check-input" id="remember">
              <label class="form-check-label" for="remember">Запомнить меня</label>
            </div>

            <button type="button" class="btn btn-light col-sm-12 mb-1">Войти</button>
          </div>


          <Transition name="slide-fade">
            <div v-show="step === 2" class="step">
              <div class="mb-5 mt-5">
                <input type="email" class="form-control" id="email" aria-describedby="emailHelp" placeholder="Ваша почта">
              </div>

              <div class="mb-5">
                <input type="email" class="form-control" id="email" aria-describedby="emailHelp" placeholder="Ваше имя (логин)">
              </div>

              <div class="mb-5">
                <input type="password" class="form-control" id="password" placeholder="Придумайте пароль">
              </div>

              <div class="mb-5">
                <input type="password" class="form-control" id="passwordConfirm" placeholder="Подтвердите пароль">
              </div>

              <div class="mb-3 form-check">
                <input type="checkbox" class="form-check-input" id="exampleCheck1">
                <label class="form-check-label" for="exampleCheck1">Принимаю условия политики конфиденциальности</label>
              </div>

              <button type="submit" class="btn btn-light col-sm-12 mb-1">Зарегистрироваться</button>

            </div>
          </Transition>

        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      step: 1
    }
  },
  methods: {
    nextStep() {
      if (this.step < 2)
        this.step++


    },
    backStep() {
      if (this.step > 1) {
        this.step--
      }

    },
    registerUser() {
      console.log('Регистрация прошла успешно');
    }
  }

}
</script>


<style>
.slide-fade-enter-active {
  transition: all 0.3s ease-out;
}


.slide-fade-enter-from{
  transform: translateX(20px);
  opacity: 0;
}
</style>
