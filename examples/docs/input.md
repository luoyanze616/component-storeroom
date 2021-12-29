<!--
注意：具有交互功能的说明文档，需要有<script></script>标签，在标签元素中定义需要导出的vue实例。
在:::demo ::: 代码块中定义的模版<template></template>会作为导出的vue实例的模版，但是在代码块中的<script></script>中的内容仅作为展示，需注意。
-->
<script>
export default {
  data () {
    return {
      value: '测试测试',
	  input2: '',
	  input3: '',
	  input4: '',
	  textarea1: '',
	  textarea2: '',
	  input_size1: '',
	  input_size2: '',
	  input_size3: '',
	  input_size4: '',
    }
  }
}
</script>
## Input
介绍Input的使用
:::demo
``` html
<template>
  <cs-input
    :value="value"
  ></cs-input>
</template>
<script>
export default {
  data () {
    return {
      value: '测试测试'
    }
  }
}
</script>
```
:::
#### 禁用状态
:::demo
``` html
<cs-input
  placeholder="请输入内容"
  v-model="input2"
  :disabled="true">
</cs-input>

<script>
export default {
  data() {
    return {
      input2: ''
    }
  }
}
</script>
```
:::
#### 可清空 
使用clearable属性可清空输入框内容      
:::demo
``` html
<cs-input
  placeholder="请输入内容"
  v-model="input3"
  clearable>
<cs-input>

<script>
  export default {
    data() {
      return {
        input3: ''
      }
    }
  }
</script>
```
:::
#### 密码框
:::demo
``` html
<cs-input placeholder="请输入密码" v-model="input4" show-password></cs-input>

<script>
  export default {
    data() {
      return {
        input: ''
      }
    }
  }
</script>
```
:::
#### 文本域
:::demo
``` html
<cs-input
  type="textarea"
  autosize
  placeholder="请输入内容"
  v-model="textarea1">
</cs-input>
<div style="margin: 20px 0;"></div>
<cs-input
  type="textarea"
  :autosize="{ minRows: 2, maxRows: 4}"
  placeholder="请输入内容"
  v-model="textarea2">
</cs-input>

<script>
export default {
  data() {
    return {
      textarea1: '',
      textarea2: ''
    }
  }
}
</script>
```
:::
#### 文本域
:::demo
``` html
<cs-input
  type="textarea"
  autosize
  placeholder="请输入内容"
  v-model="textarea1">
</cs-input>
<div style="margin: 20px 0;"></div>
<cs-input
  type="textarea"
  :autosize="{ minRows: 2, maxRows: 4}"
  placeholder="请输入内容"
  v-model="textarea2">
</cs-input>

<script>
export default {
  data() {
    return {
      textarea1: '',
      textarea2: ''
    }
  }
}
</script>
```
:::
#### 尺寸
:::demo
``` html
<div class="demo-input-size">
  <cs-input
    placeholder="请输入内容"
    suffix-icon="el-icon-date"
    v-model="input_size1">
  </cs-input>
  <div style="margin: 20px 0;"></div>
  <cs-input
    size="medium"
    placeholder="请输入内容"
    suffix-icon="el-icon-date"
    v-model="input_size2">
  </cs-input>
  <div style="margin: 20px 0;"></div>
  <cs-input
    size="small"
    placeholder="请输入内容"
    suffix-icon="el-icon-date"
    v-model="input_size3">
  </cs-input>
  <div style="margin: 20px 0;"></div>
  <cs-input
    size="mini"
    placeholder="请输入内容"
    suffix-icon="el-icon-date"
    v-model="input_size4">
  </cs-input>
</div>

<script>
export default {
  data() {
    return {
      input_size1: '',
      input_size2: '',
      input_size3: '',
      input_size4: ''
    }
  }
}
</script>
```
:::


### Input Attributes

| 参数       | 说明    |  类型   |  可选值   |  默认值   |
| --------   | :-----: | :----: | :----:   |  :----:  |
| 计算机      | \$1600  |   5    |           |           |
| 手机        |   \$12  |   12   |           |           |
| 管线        |    \$1  |   234  |           |           |

: 是对齐方向
