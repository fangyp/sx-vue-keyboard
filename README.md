# sx-vue-keyboard

Vue 手机 密码键盘

## install

```
yarn add sx-vue-keyboard
or
npm i sx-vue-keyboard
```

#### 引入插件

```javascript
import SxKeyboard from 'sx-vue-keyboard';
import 'sx-vue-keyboard/keyboard.css'
createApp(App).use(SxKeyboard).mount('#app');
```

#### 基本用法

```javascript
import { ref } from 'vue';
const keyboardRef = ref(null);

// 打开键盘
keyboardRef.value.show();
// 关闭键盘
keyboardRef.value.hide();

<sx-keyboard
ref="keyboardRef"
type="letter"
length="6"
encrypt="md5"
public-key=""
private-key=""
@complete="onFinish"
/>;

const onFinish = (value) => {
  console.log('密码 ===', value)
}
```

### API

| 参数        | 说明                                                       | 类型   | 默认值 |
| ----------- | :--------------------------------------------------------- | :----- | :----: |
| type        | 键盘类型，num: 纯数字键盘； letter: 数字、字母、字符键盘； | String |  num   |
| length      | 密码的位数，4 位密码 6 位密码 18 位以内的密码              | Number |   6    |
| ref         | 获取当前实例                                               | ref    |   -    |
| encrypt     | 加密方式，ras、md5 加密方式, ras 时必须传公钥 publicKey    | String |        |
| public-key  | 公钥，encrypt="rsa"时必传                                  | String |        |
| private-key | 私钥，公钥加密后使用 privateKey 私钥解密（测试加密用）     | String |        |

### Event

| 事件名   | 说明                 | 参数 |
| :------- | :------------------- | :--- |
| complete | 密码输入完成后的回调 | -    |

### demo 
![alt 属性文本](https://beunc.oss-cn-beijing.aliyuncs.com/github/demo.png)
