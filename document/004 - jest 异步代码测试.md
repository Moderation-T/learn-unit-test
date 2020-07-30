```javascript
// fetchData 为异步函数

// 回调类型
test('测试异步函数', (done) => {
  // 如果没有 done 未执行到回调测试就结束了 这是不对的
  fetchData(() => {
    expect(data).toEqual({ success: true });
    done(); // 只有 done 的时候测试用例才真的测试结束
  });
});

// 没有回调的类型
test('测试异步函数', (done) => {
  // 如果没有 done 未执行到回调测试就结束了 这是不对的
  return fetchData().then((res) => {
    expect(res.data).toEqual((success: true));
  });
});

// 异步返回错误
test('返回 404', () => {
  expect.assertions(1); // expect 必须执行一次
  return fetchData().catch((e) => {
    expect(e.toString().indexOf('404') > -1).toBe(true);
  });
});

// 异步测试成功
test('异步测试', () => {
  //  expect(fetchData()).resolve 返回异步调用的所有结果
  return expect(fetchData()).resolve.toMatchObject({
    data: { success: true },
  });
});

// 异步测试失败
test('404', () => {
  //  expect(fetchData()).resolve 返回异步调用的所有结果
  return expect(fetchData()).reject.toThrow();
});

// async await

// 异步测试成功
test('异步测试', async () => {
  //  expect(fetchData()).resolve 返回异步调用的所有结果
  const res = await fetchData();
  expect(res).resolve.toMatchObject({
    data: { success: true },
  });
});

// 异步测试失败
test('404', async () => {
  expect.assertions(1); // expect 必须执行一次
  //  expect(fetchData()).resolve 返回异步调用的所有结果
  try {
    await fetchData();
  } catch (e) {
    expect(e.toString()).toEqual('error msg');
  }
});
```
