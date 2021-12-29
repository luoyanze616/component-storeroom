<template lang="html">
  <button 
    class="cs-button" 
	:class="[
	  'cs-button-size-'+size,
	  'cs-button-type-'+type,
	  {
		  'is-plain' : plain,
		  'is-round' : round,
		  'is-disabled' : disabled
	  }
	]"
	:disabled="buttonDisabled"
	:plain=plain
    type="button" 
    :name="name" 
    :value="value"
    @click="buttonClick"
    @mouseenter="buttonEnter">
	  <i class="el-icon-loading" v-if="loading"></i>
	  <i :class="icon" v-if="icon && !loading"></i>
	  <span v-if="$slots.default"><slot></slot></span>
	</button>
</template>

<script>
export default {
  name: 'cs-button',
  data () {
    return{
	  
    }
  },
  // 注解3
  inject: {
	elForm: {
	  default: ''
	},
	elFormItem: {
	  default: ''
	}
  },
  props: {
    value: {
      type: String,
      default: '按钮'
    },
    name: {
      type: String,
      default: 'button'
    },
	size: {
	  type: String,
	  default: 'big'
	},
	type: {
	  type: String,
	  default: 'default'
	},
	plain: {
	  type: String,
	},
	round: {
	  type: String
	},
	disabled: {
	  type: Boolean,
	  default: false
	},
	icon: {
	  type: String,
	  default: ''
    },
	loading: Boolean,
  },
  computed: {
	// _elFormItemSize() {
	//   return (this.elFormItem || {}).elFormItemSize;
	// },
	// buttonSize() {
	//   return this.size || this._elFormItemSize || (this.$ELEMENT || {}).size;
	// },
	// 注解3
	buttonDisabled() {
	  return this.disabled || (this.elForm || {}).disabled;
	}
  },
  methods: {
    buttonClick (ev) {
      this.$emit('click', 1);
	  console.log('click end')
    },
    buttonEnter (ev) {
      this.$emit('enter', 1)
	  // console.log('enter end')
	  // console.log(this.value)
    },
  }
}
</script>

<style lang="css">
.cs-button{
  /* border: 1px solid #000;
  background: none;
  padding: 4px 8px;
  cursor: pointer;
  outline: none; */
  display: inline-block;
  line-height: 1;
  cursor: pointer;
  background: #fff;
  border: 1px solid #ddd;
  color: #fff;
  text-align: center;
  outline: none;
  font-size: 14px;
  border-radius: 4px;
}
.cs-button.cs-button-size-big {
  padding: 12px 20px;
}

.cs-button.cs-button-size-mid {
  padding: 10px 20px;
}

.cs-button.cs-button-size-small {
  padding: 8px 10px;
}

.cs-button.cs-button-size-mini {
  padding: 6px 8px;
}

.cs-button.cs-button-type-default {
  border-color: #dcdfe6;
  background-color: transparent;
  color: #606266;
}
.cs-button.cs-button-type-default:hover {
  color: #409eff;
  border-color: #c6e2ff;
  background-color: #ecf5ff;
}
.cs-button.cs-button-type-default.is-disabled:hover {
  color: #c0c4cc;
  background-color: #fff;
  border-color: #ebeef5;
}

.cs-button.cs-button-type-primary {
  background-color: #409eff;
  border-color: #409eff;
}
.cs-button.cs-button-type-primary:hover {
  background: #66b1ff;
  border-color: #66b1ff;
}

.cs-button.cs-button-type-success {
  background-color: #67c23a;
  border-color: #67c23a;
}
.cs-button.cs-button-type-success:hover {
  background: #85ce61;
  border-color: #85ce61;
}

.cs-button.cs-button-type-info {
  background-color: #909399;
  border-color: #909399;
}
.cs-button.cs-button-type-info:hover {
  background: #a6a9ad;
  border-color: #a6a9ad;
}

.cs-button.cs-button-type-warn {
  background-color: #e6a23c;
  border-color: #e6a23c;
}
.cs-button.cs-button-type-warn:hover {
  background: #ebb563;
  border-color: #ebb563;
}

.cs-button.cs-button-type-danger {
  background-color: #f56c6c;
  border-color: #f56c6c;
}
.cs-button.cs-button-type-danger:hover {
  background: #f78989;
  border-color: #f78989;
}

.cs-button.is-plain{
  border-color: #dcdfe6;
  background-color: transparent;
  color: #606266;
}
.cs-button.is-plain:hover{
  border-color: #409eff;
  background-color: #fff;
  color: #409eff;
}
.cs-button.is-plain:active{
  border-color: #3a8ee6;
  background-color: #fff;
  color: #3a8ee6;
}
.cs-button.is-plain:focus{
  border-color: #3a8ee6;
  background-color: #fff;
  color: #3a8ee6;
}
.cs-button.cs-button-type-primary.is-plain{
  border-color: #b3d8ff;
  background-color: #ecf5ff;
  color: #409eff;
}
.cs-button.cs-button-type-primary.is-plain:active{
  border-color: #409eff;
  background-color: #409eff;
  color: #fff;
}
.cs-button.cs-button-type-primary.is-plain:hover{
  border-color: #409eff;
  background-color: #409eff;
  color: #fff;
}
.cs-button.cs-button-type-primary.is-plain:focus{
  border-color: #409eff;
  background-color: #409eff;
  color: #fff;
}
.cs-button.cs-button-type-success.is-plain{
  border-color: #c2e7b0;
  background-color: #f0f9eb;
  color: #67c23a;
}
.cs-button.cs-button-type-success.is-plain:active{
  border-color: #67c23a;
  background-color: #67c23a;
  color: #fff;
}
.cs-button.cs-button-type-success.is-plain:hover{
  border-color: #67c23a;
  background-color: #67c23a;
  color: #fff;
}
.cs-button.cs-button-type-success.is-plain:focus{
  border-color: #67c23a;
  background-color: #67c23a;
  color: #fff;
}
.cs-button.cs-button-type-info.is-plain{
  border-color: #d3d4d6;
  background-color: #f4f4f5;
  color: #909399;
}
.cs-button.cs-button-type-info.is-plain:active{
  border-color: #909399;
  background-color: #909399;
  color: #fff;
}
.cs-button.cs-button-type-info.is-plain:hover{
  border-color: #909399;
  background-color: #909399;
  color: #fff;
}
.cs-button.cs-button-type-info.is-plain:focus{
  border-color: #909399;
  background-color: #909399;
  color: #fff;
}
.cs-button.cs-button-type-warn.is-plain{
  border-color: #f5dab1;
  background-color: #fdf6ec;
  color: #e6a23c;
}
.cs-button.cs-button-type-warn.is-plain:active{
  border-color: #e6a23c;
  background-color: #e6a23c;
  color: #fff;
}
.cs-button.cs-button-type-warn.is-plain:hover{
  border-color: #e6a23c;
  background-color: #e6a23c;
  color: #fff;
}
.cs-button.cs-button-type-warn.is-plain:focus{
  border-color: #e6a23c;
  background-color: #e6a23c;
  color: #fff;
}
.cs-button.cs-button-type-danger.is-plain{
  border-color: #fbc4c4;
  background-color: #fef0f0;
  color: #f56c6c;
}
.cs-button.cs-button-type-danger.is-plain:active{
  border-color: #f56c6c;
  background-color: #f56c6c;
  color: #fff;
}
.cs-button.cs-button-type-danger.is-plain:hover{
  border-color: #f56c6c;
  background-color: #f56c6c;
  color: #fff;
}
.cs-button.cs-button-type-danger.is-plain:focus{
  border-color: #f56c6c;
  background-color: #f56c6c;
  color: #fff;
}

.cs-button.is-round{
  border-radius: 20px;
  /* padding: 12px 23px; */
}
.cs-button.is-round:hover{
  border-color: #409eff;
  background-color: #fff;
  color: #409eff;
}
.cs-button.is-round:focus{
  border-color: #409eff;
  background-color: #fff;
  color: #409eff;
}
.cs-button.cs-button-type-primary.is-round{
  border-color: #b3d8ff;
  background-color: #ecf5ff;
  color: #409eff;
}
.cs-button.cs-button-type-primary.is-round:active{
  border-color: #409eff;
  background-color: #409eff;
  color: #fff;
}
.cs-button.cs-button-type-primary.is-round:focus{
  border-color: #409eff;
  background-color: #409eff;
  color: #fff;
}
.cs-button.cs-button-type-success.is-round{
  border-color: #c2e7b0;
  background-color: #f0f9eb;
  color: #67c23a;
}
.cs-button.cs-button-type-success.is-round:active{
  border-color: #67c23a;
  background-color: #67c23a;
  color: #fff;
}
.cs-button.cs-button-type-success.is-round:focus{
  border-color: #67c23a;
  background-color: #67c23a;
  color: #fff;
}
.cs-button.cs-button-type-info.is-round{
  border-color: #d3d4d6;
  background-color: #f4f4f5;
  color: #909399;
}
.cs-button.cs-button-type-info.is-round:active{
  border-color: #909399;
  background-color: #909399;
  color: #fff;
}
.cs-button.cs-button-type-info.is-round:focus{
  border-color: #909399;
  background-color: #909399;
  color: #fff;
}
.cs-button.cs-button-type-warn.is-round{
  border-color: #f5dab1;
  background-color: #fdf6ec;
  color: #e6a23c;
}
.cs-button.cs-button-type-warn.is-round:active{
  border-color: #e6a23c;
  background-color: #e6a23c;
  color: #fff;
}
.cs-button.cs-button-type-warn.is-round:focus{
  border-color: #e6a23c;
  background-color: #e6a23c;
  color: #fff;
}
.cs-button.cs-button-type-danger.is-round{
  border-color: #fbc4c4;
  background-color: #fef0f0;
  color: #f56c6c;
}
.cs-button.cs-button-type-danger.is-round:active{
  border-color: #f56c6c;
  background-color: #f56c6c;
  color: #fff;
}
.cs-button.cs-button-type-danger.is-round:focus{
  border-color: #f56c6c;
  background-color: #f56c6c;
  color: #fff;
}

.cs-button.cs-button-type-primary.is-round:hover {
  background: #66b1ff;
  border-color: #66b1ff;
  color: #fff;
}

.cs-button.cs-button-type-success.is-round:hover {
  background: #85ce61;
  border-color: #85ce61;
  color: #fff;
}

.cs-button.cs-button-type-info.is-round:hover {
  background: #a6a9ad;
  border-color: #a6a9ad;
  color: #fff;
}

.cs-button.cs-button-type-warn.is-round:hover {
  background: #ebb563;
  border-color: #ebb563;
  color: #fff;
}

.cs-button.cs-button-type-danger.is-round:hover {
  background: #f78989;
  border-color: #f78989;
  color: #fff;
}

.cs-button.is-disabled{
  color: #c0c4cc;
  cursor: not-allowed;
  background-image: none;
  background-color: #fff;
  border-color: #ebeef5;
}
.cs-button.cs-button-type-primary.is-disabled{
  color: #fff;
  background-color: #a0cfff;
  border-color: #a0cfff;
}
.cs-button.cs-button-type-success.is-disabled{
  color: #fff;
  background-color: #b3e19d;
  border-color: #b3e19d;
}
.cs-button.cs-button-type-info.is-disabled{
  color: #fff;
  background-color: #c8c9cc;
  border-color: #c8c9cc;
}
.cs-button.cs-button-type-warn.is-disabled{
  color: #fff;
  background-color: #f3d19e;
  border-color: #f3d19e;
}
.cs-button.cs-button-type-danger.is-disabled{
  color: #fff;
  background-color: #fab6b6;
  border-color: #fab6b6;
}
.cs-button.is-disabled.is-round{
  color: #c0c4cc;
  background-color: #fff;
  border-color: #ebeef5;
}
.cs-button.cs-button-type-primary.is-disabled.is-round{
  color: #fff;
  background-color: #a0cfff;
  border-color: #a0cfff;
}
.cs-button.cs-button-type-success.is-disabled.is-round{
  color: #fff;
  background-color: #b3e19d;
  border-color: #b3e19d;
}
.cs-button.cs-button-type-info.is-disabled.is-round{
  color: #fff;
  background-color: #c8c9cc;
  border-color: #c8c9cc;
}
.cs-button.cs-button-type-warn.is-disabled.is-round{
  color: #fff;
  background-color: #f3d19e;
  border-color: #f3d19e;
}
.cs-button.cs-button-type-danger.is-disabled.is-round{
  color: #fff;
  background-color: #fab6b6;
  border-color: #fab6b6;
}

</style>
