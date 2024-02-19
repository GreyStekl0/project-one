<script setup>
import {ref} from "vue";

const name = ref("");
const question = ref("");
const phone = ref("");
const email = ref("");
const success = ref(false);

async function onSubmit() {
  console.log(name.value,
      question.value,
      phone.value,
      email.value)

  const botToken = "6575469349:AAHKsvnpsMTWhFFejRIG9FuE3rkwkH5l0nk";
  const chatId = "-1002132065597";
  const text = `Новое сообщение:%0A%0A ` +
      `Вопрос: ${name.value}%0A ` +
      `Имя: ${question.value}%0A ` +
      `Телефон: ${phone.value}%0A ` +
      `Электронная почта: ${email.value}`;
  await fetch(`https://api.telegram.org/bot${botToken}/sendMessage?chat_id=${chatId}&text=${text}`)
      .then((responce) => {
        if (responce.status === 200) {
          success.value = true;
        }
      })
      .catch((error) => {
        success.value = false;
        console.log(error);
      });
  const message = success.value ? "Сообщение отправлено" : "Ошибка отправки";
  alert(message);
  name.value='';
  question.value='';
  phone.value='';
  email.value=''
}

</script>

<template>
  <section class="feedback">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-xl-6">
          <div class="feedback__text">
            <h2>Остались вопросы?</h2>
            <p>Свяжитесь с нами!</p>
          </div>
        </div>
        <div class="col-lg-9 col-xl-6">
          <form class="form" method="post" @submit.prevent="onSubmit">
            <label class="mb-3">
                                <textarea placeholder="Введите ваш вопрос"
                                          title="Введите ваш вопрос"
                                          v-model="question"
                                          required>
                                </textarea>
            </label>
            <div class="form__group">
              <label>
                <input type="text" placeholder="Ваше имя"
                       title="Ваше имя"
                       v-model="name"
                       required>
              </label>
              <label>
                <input type="tel"
                       placeholder="+7(___)___-____"
                       pattern="[0-9]{11}"
                       maxlength="11"
                       title="номер телефона"
                       v-model="phone"
                       required>
              </label>
              <label>
                <input type="email" placeholder="Электронная почта"
                       title="Электронная почта"
                       v-model="email"
                       required>
              </label>
            </div>
            <button class="button-primary" type="submit">Отправить</button>
          </form>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>

</style>