<script>
export default {
  data () {
    return {
      value: '我是按钮'
    }
  },
  methods: {
    click () {
      this.value = '我点击过'
    }
  }
}
</script>
## Button
介绍Button的使用
:::demo
``` html
<template>
  <div>
	<cs-button :value="value" @click="click">默认按钮</cs-button>
	<cs-button :value="value" type="primary" @click="click">主要按钮</cs-button>
	<cs-button :value="value" type="success" @click="click">成功按钮</cs-button>
	<cs-button :value="value" type="info" @click="click">信息按钮</cs-button>
	<cs-button :value="value" type="warn" @click="click">警告按钮</cs-button>
	<cs-button :value="value" type="danger" @click="click">危险按钮</cs-button>
  </div>
  <p/>
  <div>
  	<cs-button :value="value" plain="plain" @click="click">朴素按钮</cs-button>
  	<cs-button :value="value" type="primary" plain="plain" @click="click">主要按钮</cs-button>
  	<cs-button :value="value" type="success" plain="plain" @click="click">成功按钮</cs-button>
  	<cs-button :value="value" type="info" plain="plain" @click="click">信息按钮</cs-button>
  	<cs-button :value="value" type="warn" plain="plain" @click="click">警告按钮</cs-button>
  	<cs-button :value="value" type="danger" plain="plain" @click="click">危险按钮</cs-button>
  </div>
  <p/>
  <div>
  	<cs-button :value="value" round="round" @click="click">圆角按钮</cs-button>
  	<cs-button :value="value" type="primary" round="round" @click="click">主要按钮</cs-button>
  	<cs-button :value="value" type="success" round="round" @click="click">成功按钮</cs-button>
  	<cs-button :value="value" type="info" round="round" @click="click">信息按钮</cs-button>
  	<cs-button :value="value" type="warn" round="round" @click="click">警告按钮</cs-button>
  	<cs-button :value="value" type="danger" round="round" @click="click">危险按钮</cs-button>
  </div>
  <p/>
</template>
<script>
export default {
  data () {
    return {
      value: '我是按钮'
    }
  },
  methods: {
    click () {
      this.value = '我点击过'
    }
  }
}
</script>
```
:::
禁用状态 disabled="disabled"
:::demo
``` html
<template>
  <div>
  	<cs-button :value="value" disabled="disabled" >{{value}}</cs-button>
  	<cs-button :value="value" type="primary" disabled="disabled" >{{value}}</cs-button>
  	<cs-button :value="value" type="success" disabled="disabled" >{{value}}</cs-button>
  	<cs-button :value="value" type="info" disabled="disabled" >{{value}}</cs-button>
  	<cs-button :value="value" type="warn" disabled="disabled" >{{value}}</cs-button>
  	<cs-button :value="value" type="danger" disabled="disabled" >{{value}}</cs-button>
  </div>
  <p/>
  <div>
  	<cs-button :value="value" round="round" disabled="disabled" >{{value}}</cs-button>
  	<cs-button :value="value" type="primary" disabled="disabled" round="round" >{{value}}</cs-button>
  	<cs-button :value="value" type="success" disabled="disabled" round="round" >{{value}}</cs-button>
  	<cs-button :value="value" type="info" disabled="disabled" round="round" >{{value}}</cs-button>
  	<cs-button :value="value" type="warn" disabled="disabled" round="round" >{{value}}</cs-button>
  	<cs-button :value="value" type="danger" disabled="disabled" round="round" >{{value}}</cs-button>
  </div>
  <p/>
</template>
<script>
export default {
  data () {
    return {
      value: '我是按钮'
    }
  },
  methods: {
    click () {
      this.value = '我点击过'
    }
  }
}
</script>
```
:::
不同尺寸
:::demo
``` html
<template>
  <div>
  	<cs-button plain="plain" @click="click">default</cs-button>
  	<cs-button size="mid" type="primary" plain="plain" @click="click">midd</cs-button>
  	<cs-button size="small" type="success" plain="plain" @click="click">small</cs-button>
  	<cs-button size="mini" type="info" plain="plain" @click="click">mini</cs-button>
  </div>
  <p/>
  <div>
  	<cs-button round="round" @click="click">default</cs-button>
  	<cs-button size="mid" type="primary" round="round" @click="click">mid</cs-button>
  	<cs-button size="small" type="success" round="round" @click="click">small</cs-button>
  	<cs-button size="mini" type="info" round="round" @click="click">mini</cs-button>
  </div>
  <p/>
</template>
<script>
export default {
  data () {
    return {
      value: '我是按钮'
    }
  },
  methods: {
    click () {
      this.value = '我点击过'
    }
  }
}
</script>
```
:::
### Button Attributes

| 参数      | 说明    |  类型   |  可选值  |  默认值   |
| -------- | :-----: | :----: | :----:   |  :----:  |
| type | 类型 |  string  | primary、success、info、warn、danger | default |
| plain |  朴素  |  string  |  plain  |  plain*必填  |
| round |  圆角  |  string  |  round  |  round*必填  |
| disabled |  禁用  |  string  |  disabled  |  disabled*必填  |
| size |  大小  |  string  |  big、mid、small、mini  |  big  |
: 是对齐方向