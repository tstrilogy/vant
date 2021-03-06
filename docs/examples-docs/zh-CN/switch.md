<style>
.demo-switch {
  .van-switch {
    margin: 0 15px;
  }
}
</style>

<script>
import Dialog from 'packages/dialog';

export default {
  data() {
    return {
      checked: true,
      checked2: true
    };
  },

  methods: {
    onInput(checked) {
      Dialog.confirm({
        title: '提醒',
        message: '是否切换开关？'
      }).then(() => {
        this.checked2 = checked;
      });
    }
  }
};  
</script>

## Switch 开关

### 使用指南
``` javascript
import { Switch } from 'vant';

Vue.component(Switch.name, Switch);
```

### 代码演示

#### 基础用法

:::demo 基础用法
```html
<van-switch v-model="checked" />
```

```javascript
export default {
  data() {
    return {
      checked: true
    };
  }
};  
```
:::

#### 禁用状态
:::demo 禁用状态
```html
<van-switch v-model="checked" disabled />
```
:::

#### 加载状态
:::demo 加载状态
```html
<van-switch v-model="checked" loading />
```
:::

#### 高级用法
:::demo 高级用法
```html
<van-switch :value="checked2" @input="onInput" />
```
```js
export default {
  data() {
    return {
      checked2: true
    };
  },

  methods: {
    onInput(checked) {
      Dialog.confirm({
        title: '提醒',
        message: '是否切换开关？'
      }).then(() => {
        this.checked2 = checked;
      });
    }
  }
}; 
```
:::


### API

| 参数 | 说明 | 类型 | 默认值 | 可选值 |
|-----------|-----------|-----------|-------------|-------------|
| v-model | 开关选中状态 | `Boolean`  | `false` | - |
| loading | 是否为加载状态 | `Boolean`  | `false` | - |
| disabled | 是否为禁用状态 | `Boolean`  | `false` | - |

### Event

| 事件名       | 说明      | 参数       |
|-----------|-----------|-----------|
| change | 开关状态切换回调 | checked: 是否选中开关 |
