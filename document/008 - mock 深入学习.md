- 编写文件替换真是代码进行数据模拟
```js
// 新建 __mocks__ 文件夹 在里边新建文件编写要模拟的代码

jest.mock('./demo' )
jest.unmock('./demo')

// jest.config.js

automock:true. // 自动使用 mock 文件

// mock 的文件中没有相应的函数 使用
const {getNumber} = jest.requireActual('./demo') // 去引用真实文件下的函数
```

- mock timers 对定时器进行模拟

```js
test('定时器测试',(done)=>{
  timer(()=>{
    console.log('timer 是一个定时器函数 三秒之后执行');
    done() // 这样就会等到 timer 执行完成后结束测试
  })
})

// mock 定时器
jest.useFakeTimers(); 

test('模拟定时器',()=>{
  const fn = jest.fn();
  timer(fn);
  jest.runAllTimers(); // 立即实行定时函数 执行所有定时器
  jest.runOnlyPendingTimers(); // 只运行处于运行中的 tiemr
  jest.advancedTimersByTime(3000) // 让时间快进 3s  
  expect(fn).toHaveBeenCalledTimers(1);  // 预期 fn 被执行了一次
});
```