### <a name="deserialization-of-objects-across-appdomains-can-fail"></a>跨应用域的对象的反序列化可能失败

|   |   |
|---|---|
|详细信息|在某些情况下，当应用使用两个或更多带有不同应用程序基的应用域时，尝试跨应用域在逻辑调用上下文中为对象反序列化将引发异常。|
|建议|请参阅[缓解：跨应用程序域的对象的反序列化](~/docs/framework/migration-guide/mitigation-deserialization-of-objects-across-app-domains.md)|
|范围|边缘|
|版本|4.5.1|
|类型|运行时|

