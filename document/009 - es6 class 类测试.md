```js
// util.js
class Util {
  a(){},
  b(){}
}
```

```js
// test.js
// jest.mock 发现 util 是一个类，会自动把类的构造函数和方法变成 jest.fn() 提高测试性能
jest.mock('./util');
import Util from './util'
import demoFunction from './demo'

test('测试类函数',()=>{
  demoFunction()
  expect(Util).toHaveBeenCalled()
  expect(Util.mock.instances[0].a).toHaveBeenCalled()
  expect(Util.mock.instances[0].b).toHaveBeenCalled()
})

```
