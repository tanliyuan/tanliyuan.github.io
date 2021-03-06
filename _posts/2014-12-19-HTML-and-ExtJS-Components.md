---
layout: article
title: Json data binding filters
category: tech
tags: Jackson Java Json Data-Binding 
description: Jackson - Data Binding序列化和反序列化Java对象中filters的使用实例
---

## renderTpl and renderData

http://skirtlesden.com/articles/html-and-extjs-components
Extjs的config选项`renderTpl`、`renderData`和`tpl`、`data`有些类似，但是前两个只在组件初始化渲染的时候运行一次。`renderTpl`和`tpl`都是用来创建组件内在标签的，但是`renderTpl`创建的元素会作为组件自己标签的一部分，而不是组件内容部分。

例如，panel中使用`tpl`，`tpl`负责渲染面板的动态内容，Panel类也有一个`renderTpl`，这个`renderTpl`用来创建面板元素的脚手架，含有header,toolbars和body。

`tpl`可能出现在类定义或是实例化的时候，然而`renderTpl`只可能出现在类定义中。

{% highlight java linenos %}

class Zoo {
    public String name;
    public String city;
 
     
    @JsonCreator
    public Zoo(@JsonProperty("name") String name,@JsonProperty("city") String city) {
        this.name = name;
        this.city = city;
    }
 
    public List<Animal> animals = new ArrayList<Animal>();
 
    public List<Animal> addAnimal(Animal animal) {
        animals.add(animal);
        return animals;
    }
 
}

{% endhighlight  %} 


教程标题| 主要内容
-------|----------
关于Markdown | 简介Markdown，Markdown的优缺点
Markdown基础 | Markdown的**基本语法**，格式化文本、代码、列表、链接和图片、分割线、转义符等
Markdown表格和公式 | Markdown的**扩展语法**，表格、公式
