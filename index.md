# Revit 接口示例

## Template

```php
    Set[Value]='Pset_WallCommon' AND Property[Value]='IsExternal'
```

### Set

```c++
     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                -> RelatingPropertyDefinition [IfcPropertySet]  
                -> Name
     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                -> RelatingPropertyDefinition [IfcElementQuantity]  
                -> Name
```

### Property

*     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                 -> RelatingPropertyDefinition [IfcPropertySet]  
                 -> HasProperties [IfcSimpleProperty]  
                 -> Name
*     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                 -> RelatingPropertyDefinition [IfcPropertySet]  
                 -> HasProperties [IfcPropertySingleValue]  
                 -> Name
*     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                 -> RelatingPropertyDefinition [IfcPropertySet]  
                 -> HasProperties [IfcPropertyEnumeratedValue]  
                 -> Name
*     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                 -> RelatingPropertyDefinition [IfcPropertySet]  
                 -> HasProperties [IfcPropertyEnumeratedValue]  
                 -> EnumerationReference [IfcPropertyEnumeration]  
                 -> Name
*     IfcProduct -> IsDefinedBy [IfcRelDefinesByProperties]  
                 -> RelatingPropertyDefinition [IfcElementQuantity]  
                 -> Quantities [IfcPhysicalSimpleQuantity]  
                 -> Name

### 生成信息

#### 属性集

* `Pset : Pset_WallCommon`
* `Key : IsExternal`
* `实例属性`

#### 算量集

* `Qset : Pset_WallCommon`
* `Key : IsExternal`
* `实例属性`

#### 关系

* `Rel : IsDefindBy [IfcRelDefinesByProperties]`
* `FromAttribute : RelatedObjects`
* `ToAttribute : RelatingPropertyDefinition`
