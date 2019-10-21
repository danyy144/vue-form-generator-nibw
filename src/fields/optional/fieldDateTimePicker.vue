<template>

          <datetime  
          type="datetime"
          v-model="value"          
          use12-hour
          moment-locale="es"
          :format="schema.format"
          :disabled="disabled"
          :placeholder="schema.placeholder"
          :readonly="schema.readonly"
          :min-datetime="schema.min"
          :max-datetime="schema.max"
          ></datetime>

</template>

<script>
import abstractField from "../abstractField";
import dateFieldHelper from "../../utils/dateFieldHelper";

import {Datetime} from "vue-datetime";

// You need a specific loader for CSS files
import "vue-datetime/dist/vue-datetime.css";


let inputFormat = "YYYY-MM-DD HH:mm:ss";

export default {
     mixins: [abstractField],
     components: {
          Datetime
     },

	methods: {
		getDateFormat() {
			if (this.schema && this.schema.format) return this.schema.format;
			else return inputFormat;
		},
		...dateFieldHelper
	},

	mounted() {

	},

	beforeDestroy() {

	}
};
</script>


<style>
.vdatetime-input {
     display: block;
     width: 100%;
     height: calc(1.5em + 0.75rem + 2px);
     padding: 0.375rem 0.75rem;
     font-size: 1rem;
     font-weight: 400;
     line-height: 1.5;
     color: #495057;
     background-color: #fff;
     background-clip: padding-box;
     border: 1px solid #ced4da;
     border-radius: 0.25rem;
     -webkit-transition: border-color 0.15s ease-in-out,
          -webkit-box-shadow 0.15s ease-in-out;
     transition: border-color 0.15s ease-in-out,
          -webkit-box-shadow 0.15s ease-in-out;
     transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out;
     transition: border-color 0.15s ease-in-out, box-shadow 0.15s ease-in-out,
          -webkit-box-shadow 0.15s ease-in-out;
}
.vdatetime-popup__header {
     background: #031561;
}
.vdatetime-month-picker__item--selected {
     color: #031561;
}
.vdatetime-popup__actions__button {
     color: #031561;
}
.vdatetime-year-picker__item--selected {
     color: #031561;
     font-size: 32px;
}
.vdatetime-calendar__month__day--selected > span > span,
.vdatetime-calendar__month__day--selected:hover > span > span {
     background: #031561;
}

</style>
