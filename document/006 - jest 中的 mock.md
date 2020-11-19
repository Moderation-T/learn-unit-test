- jest 中的 mock 函数

  > jest.fn() 模拟一个函数 ，捕获一个函数的调用' 可以让我们自由的设置返回结果

  ```js
  const func = j est.fn();
  expect(func).toBeCalled(); 函数调用 成功
  expect(func.mock.calls.length).toBe(2); 被调用 2 次
  func.mockReturnValue('value'); 第一次执行的返回值
  func.mockImplementation(()=>{
    console.log(23333)
    return 'value'
  })
  func.mockImplementationOnce('value1')
  func.mockReturnValueOnce('value'); 第一次执行的返回值
  func.mockReturnValueOnce('value1').mockReturnValueOnce('value2 '); 第一次执行的返回值
  expect(func).toBeCalledWith('abc') 每次调用返回的都是 abc
  ```

> jest.mock('axios') // 改变函数的内部数显

```js
// 改变axios.get 的返回
axios.get.mockResolvedValue({data:'hello'})
await getData().then((data)=>{expect(data).toBe('hello)})
```
