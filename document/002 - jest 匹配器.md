- 匹配器

  > toBe `expect(10).toBe(10)` 类似 ===
  > toEqual `expect({a:10}).toEqual({a:10})` 引用类型只匹配内容
  > toBeNull `expect(a).toNull()`
  > toBeUndefined `expect(a).toBeUndefined()`
  > toBeDefined `expect(a).toBeDefined()`
  > toBeTruthy `expect(a).toBeTruthy()` 是否为真
  > toBeFalsy `expect(a).toBeFalsy()` 是否为假
  > .not `expect(a).not.toBeFalsy()` not 为取反

- 数字相关匹配器

  > toBeGreaterThan `expect(10).toBeGreaterThan(11)` 比谁大
  > toBeLessThan `expect(11).toBeGreaterThan(10)` 比谁小
  > toBeGreaterThanOrEqual 大于等于
  > toBeLessThanOrEqual 小于等于
  > toBeCloseTo 比较浮点数的时候

- 字符串相关匹配器

  > toMatch 字符串中是否包含某字符串
  > toMatchObject 对象中是否包含某一块内容

- 和 Array Set 相关的匹配器

  > toContain 数组中是否包含某一项

- 异常匹配器

  > toThrow `expect(throwErrorFun).toThrow()`