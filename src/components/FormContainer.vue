<template>
  <div class="form-container">
    <h1 class="heading-main">Регистрация клиента</h1>
    <div class="dash">

    </div>
    <h3 class="heading">Основная информация:</h3>
    <p>
      <input
        type="text"
        placeholder="Фамилия*"
        v-model="state.personalInfo.firstName"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.personalInfo.firstName.$error">
      {{
        errorTranslator[v$.personalInfo.firstName.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Имя*"
        v-model="state.personalInfo.lastName"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.personalInfo.lastName.$error">
      {{
        errorTranslator[v$.personalInfo.lastName.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Отчество"
        v-model="state.personalInfo.patronymic"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.personalInfo.patronymic.$error">
      {{
        errorTranslator[v$.personalInfo.patronymic.$errors[0].$message]
      }}
    </p>
    <p class="input-heading">Дата рождения:</p>
    <p>
      <input
        type="date"
        placeholder="Дата рождения*"
        v-model="state.personalInfo.birthDate"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.personalInfo.birthDate.$error">
      {{
        errorTranslator[v$.personalInfo.birthDate.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="tel"
        placeholder="Номер телефона*"
        v-model="state.personalInfo.phone"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.personalInfo.phone.$error">
      {{
        errorTranslator[v$.personalInfo.phone.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Пол"
        v-model="state.personalInfo.sex"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.personalInfo.sex.$error">
      {{
        errorTranslator[v$.personalInfo.sex.$errors[0].$message]
      }}
    </p>
    <p class="input-heading">Группа клиентов*:</p>
    <p>
      <input type="checkbox" id="1" class="checkbox-input" v-model="state.personalInfo.clientGroup.vip">
      <label for="1" class="checkbox-label">VIP</label>
      <input type="checkbox" id="2" class="checkbox-input" v-model="state.personalInfo.clientGroup.problem">
      <label for="2" class="checkbox-label">Проблемные</label>
      <input type="checkbox" id="3" class="checkbox-input" v-model="state.personalInfo.clientGroup.oms">
      <label for="3" class="checkbox-label">ОМС</label>
    </p>
    <p class="error" v-if="v$.personalInfo.clientGroup.vip.$error">
      {{
        errorTranslator[v$.personalInfo.clientGroup.$errors[0].$message]
      }}
    </p>
    <p>
      <select
        v-model="state.personalInfo.attPhysician"
        class="text-input"
      >
        <option disabled value="">Лечащий врач</option>
        <option></option>
        <option>Иванов</option>
        <option>Захаров</option>
        <option>Чернышева</option>
      </select>
    </p>
    <p class="error" v-if="v$.personalInfo.attPhysician.$error">
      {{
        errorTranslator[v$.personalInfo.attPhysician.$errors[0].$message]
      }}
    </p>
    <p>
      <input type="checkbox" id="noSMS" class="checkbox-input" v-model="state.personalInfo.noSMS">
      <label for="noSMS" class="checkbox-label">Не отправлять СМС</label>
      <br>
    </p>
    <p class="error" v-if="v$.personalInfo.noSMS.$error">
      {{
        errorTranslator[v$.personalInfo.noSMS.$errors[0].$message]
      }}
    </p>
    
    
    <h3 class="heading">Адрес:</h3>
    <p>
      <input
        type="text"
        placeholder="Индекс"
        v-model="state.adress.index"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.adress.index.$error">
      {{
        errorTranslator[v$.adress.index.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Страна"
        v-model="state.adress.country"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.adress.country.$error">
      {{
        errorTranslator[v$.adress.country.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Область"
        v-model="state.adress.region"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.adress.region.$error">
      {{
        errorTranslator[v$.adress.region.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Город*"
        v-model="state.adress.town"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.adress.town.$error">
      {{
        errorTranslator[v$.adress.town.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Улица"
        v-model="state.adress.street"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.adress.street.$error">
      {{
        errorTranslator[v$.adress.street.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Дом"
        v-model="state.adress.building"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.adress.building.$error">
      {{
        errorTranslator[v$.adress.building.$errors[0].$message]
      }}
    </p>
    
    
    <h3 class="heading">Документ, подтверждающий личность:</h3>
    <p>
      <select
        v-model="state.passport.type"
        class="text-input"
      >
        <option disabled value="">Тип документа</option>
        <option>Паспорт</option>
        <option>Свидетельство о рождении</option>
        <option>Водительские права</option>
      </select>
    </p>
    <p class="error" v-if="v$.passport.type.$error">
      {{
        errorTranslator[v$.passport.type.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Серия"
        v-model="state.passport.series"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.passport.series.$error">
      {{
        errorTranslator[v$.passport.series.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Номер"
        v-model="state.passport.number"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.passport.number.$error">
      {{
        errorTranslator[v$.passport.number.$errors[0].$message]
      }}
    </p>
    <p>
      <input
        type="text"
        placeholder="Кем выдан"
        v-model="state.passport.givingPlace"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.passport.givingPlace.$error">
      {{
        errorTranslator[v$.passport.givingPlace.$errors[0].$message]
      }}
    </p>
    <p class="input-heading">Когда выдан:</p>
    <p>
      <input
        type="date"
        placeholder="Когда выдан"
        v-model="state.passport.givingDate"
        class="text-input"
      />
    </p>
    <p class="error" v-if="v$.passport.givingDate.$error">
      {{
        errorTranslator[v$.passport.givingDate.$errors[0].$message]
      }}
    </p>


    <button
      @click="submitForm"
      class="button"
    >
      Отправить
    </button>
  </div>
</template>

<script>
import useVuelidate from '@vuelidate/core';
import { required, minLength, maxLength, helpers } from '@vuelidate/validators';
import { reactive, computed } from 'vue';

export default {
  setup() {
    const state = reactive({
      personalInfo: {
        firstName: '',
        lastName: '',
        patronymic: '',
        birthDate: '',
        phone: '',
        sex: '',
        clientGroup: {
          vip: false,
          problem: false,
          oms: false
        },
        attPhysician: '',
        noSMS: false
      },
      adress: {
        index: '',
        country: '',
        region: '',
        town: '',
        street: '',
        building: ''
      },
      passport: {
        type: '',
        series: '',
        number: '',
        givingPlace: '',
        givingDate: ''
      }
    });

    const firstNumberIsSeven = value => value[0] === '7';

    const rules = computed(() => {
      return {
        personalInfo: {
          firstName: { required },
          lastName: { required },
          patronymic: {  },
          birthDate: { required },
          phone: { required, minLength: minLength(11), maxLength: maxLength(11), firstNumberIsSeven: helpers.withMessage('Первая цифра телефона должна быть 7', firstNumberIsSeven) },
          sex: {  },
          clientGroup: {
            vip: { clientGroupRequired: helpers.withMessage('Value is required', clientGroupRequired) },
            problem: { clientGroupRequired },
            oms: { clientGroupRequired }
          },
          attPhysician: {  },
          noSMS: {  }
        },
        adress: {
          index: {  },
          country: {  },
          region: {  },
          town: { required },
          street: {  },
          building: {  }
        },
        passport: {
          type: { required },
          series: {  },
          number: {  },
          givingPlace: {  },
          givingDate: { required }
        }
      }
    });

    const errorTranslator = {
      'Value is required': 'Поле надо обязательно заполнить',
      'This field should be at least 11 long': 'Длина телефонного номера должна быть 11',
      'The maximum length allowed is 11': 'Длина телефонного номера должна быть 11',
      'Первая цифра телефона должна быть 7': 'Первая цифра телефона должна быть 7'
    };

    const clientGroupRequired = () => state.personalInfo.clientGroup.vip || state.personalInfo.clientGroup.problem || state.personalInfo.clientGroup.oms

    const v$ = useVuelidate(rules, state);

    return {
      state,
      v$,
      errorTranslator
    }
  },
  methods: {
    submitForm() {
      this.v$.$validate();
      if (!this.v$.$error) {
        alert('Клиент успешно зарегистрирован');
      } else {
        alert('Проверьте заполненные поля');
      }
    }
  }
};
</script>

<style lang='scss'>
input {outline: 0 !important;}
.form-container {
  padding: 50px;
  width: 30vw;
  margin: 0 auto;
  min-width: 300px;
}
.text-input {
  width: 20vw;
  min-width: 300px;
  font-size: 150%;
  border: 2px solid rgb(95, 95, 95);
  border-width: 0 0 2px 0;
  padding: 5px 10px;
  box-sizing: border-box;
  border-radius: 5px;
  &:focus {
    border: 2px solid rgb(43, 43, 43);
    background: rgb(233, 233, 233);
  }
  color: rgb(0, 0, 0);
}
.checkbox-input {
  transform:scale(1.3);
  opacity:0.9;
  cursor:pointer;
  margin-left: 1vw;
}
.checkbox-label {
  font-size: 120%;
  margin-left: 1vw;
  margin-right: 1vw;
}
.error {
  color: rgb(194, 0, 0);
  font-size: 120%;
  margin: 0;
}
.button {
  min-width: 150px;
  width: 10vw;
  height: fit-content;
  padding: 10px 0;
  font-size: 150%;
  border: 2px solid rgb(43, 43, 43);
  border-radius: 5px;
  background: rgb(255, 255, 255);
  color: rgb(95, 95, 95);
  margin: 20px;
  &:hover {
    border: 2px solid rgb(43, 43, 43);
    background: rgb(233, 233, 233);
  }
  &:focus {
    border: 2px solid rgb(43, 43, 43);
    background: rgb(233, 233, 233);
  }
}
.heading-main {
  font-size: 300%;
}
.heading {
  font-size: 200%;
  margin: 40px 0 0 0;
}
.dash {
  width: 100%;
  height: 2px;
  border: 2px solid black;
  border-radius: 100% 100% 100% 100%;
}
.input-heading {
  font-size: 150%;
  margin: 0;
}
</style>