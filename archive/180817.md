# 本周工作内容

* MVD 校验库与 Revit / Xbim 插件部分的对接准备

---

## Revit

* 对外接口确定
* MVD 解析暂时忽略规则逻辑，只提供规则中涉及的属性

---

## Xbim 插件

* MVD 校验部分与 IFC 解析部分解耦
> * 动态加载 nupkg 导致程序集加载异常使类型判断失效
> * 更换 IFC 解析库时需要重写部分代码

---

## IFC 解析与 MVD 校验

MVD 校验需要获得 IFC 实例对象及其属性信息

旧做法通过反射实现，依赖于 StepParser 项目

* 类型
* 程序集
* 属性的实现

---
    
    !csharp
    // ...
    interface IMVDType
    {
        Type GetIfcType();
    }

    interface IMVDEntity
        : IMVDType
    {
        IMVDType GetAttribute(string attrName);
    }

    interface IMVDEntityCollection
        : IMVDType,
        IEnumerable<IMVDType> {}
    // ...


















