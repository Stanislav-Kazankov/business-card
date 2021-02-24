<template>
  <section class="page">
    <div class="page__centerer">
      <h1 class="page__h1">Мои контакты:</h1>
      <ul class="contacts">
        <li class="contacts__item"
          v-for="(contact, index) of contactData"
          :key="index"
        >   {{contact.caption}}:
          <a class="contacts__link"
            :href="contact.url">
            {{contact.value}}
          </a>
        </li>
      </ul>
    </div>
  </section>
</template>

<style lang="scss" scoped>
  .contacts {
    padding-left: 0;

    list-style: none;

    &__item {
      margin-bottom: 10px;
    }

    &__link {
      position: relative;

      &:after {
        content: '';

        position: absolute;
        left: 0;
        bottom: 0;

        width: 100%;
        height: 2px;

        background-color: #76a704;
      }
    }
  }
</style>

<script>
  export default {
    data() {
      return {
        contactData: [
          {
            caption: 'Телефон',
            url: 'tel:+79245180731',
            value: '+7-924-518-0731',
          },
          {
            caption: 'Email',
            url: 'mailto:s.v.kazankov@mail.ru',
            value: 's.v.kazankov@mail.ru',
          },
          {
            caption: 'Telegram',
            url: 'https://telegram.me/s_v_kazankov',
            value: '@s_v_kazankov',
          },
        ]
      }
    }
  }
</script>