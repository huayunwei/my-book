## Input

* name：input元素的名称，用于对提交到服务器后的表单数据进行标识

* accept：只和type=file配合使用，规定上传的文件类型

* alt：只和type=image配合使用，设置图片的描述

* checked：只和type=radio,checkbox配合使用，规定默认选中

* disabled：无法和type=hidden配合使用，禁用input元素

* readonly：输入字段为只读，不能修改

* maxlength：输入字段的最长长度，以字符个数计算，只能和type=text,password配合

* src：只和type=image配合，图片提交按钮的图片地址

* value：input元素设定值

* autocomplete：开启或关闭自动完成功能，默认为on

* autofocus：加载时自动获得焦点

* multiple：使用type=file，可以选择多个值

* pattern：验证input

* placeholder：提供占位符文字，在输入为空时显示

* required：在提交之前必须填写，不能为空

* form：规定非form标签内的元素，输入那个form表单

* formaction：重写表单的action属性

* formenctype：重写enctype属性

* formmethod：重写method属性

* formnovalidate：重写novalidate属性

* formtarget：重写target属性

* type：规定input元素的类型\(图片为chrome下的显示\)

  * button：按钮，value属性的值为按钮上显示的文字，类似[button标签](/HTML/label/form/form_button.md)

  * checkbox：多选按钮，同一组按钮name必须一致

    * 支持checked属性，代表默认选中

    ```markdown
    <input type="checkbox" checked />
    ```

  * file：用于文件的上传

    * 上传文件前

    ![](/assets/label_input_file_prev.png)

    * 上传文件后

    ![](/assets/label_input_file_next.png)

    * 上传文件进度

    ```
    http://blog.csdn.net/qq_36687640/article/details/78551217
    ```

    * 支持accept和multiple属性

    ```markdown
    //accept属性，默认上传时选择的为全部类型的文件
    //accept中指定默认上传的类型，用逗号分割，在用户选择上传时可以手动修改类型上传，不会报错
    <input type="file" accept="image/gif,image/jpeg,image/jpg" />

    //multiple属性，默认上传时只能选择一个文件，添加后可以选择多个文件一起上传
    <input type="file" multiple />
    ```

  * hidden：隐藏不可见，但是数据仍然可以被提交

  * image：图片型提交按钮

    * src属性：图片地址

    * alt：图片描述，默认为提交

    * width，height：图片宽高

  * password：密码框，和text外观一样，但是输入的内容不可见

    * 通过将input的type属性修改为text可以达到密码可见的效果

    ![](/assets/label_input_password.png)

  * radio：单选按钮，同一组按钮name必须一致

    * 支持checked属性，默认选中，同一组按钮，都设置checked，最后一个被选中

    ```markdown
    <input type="radio" checked/>
    ```

  * reset：创建重置表单的按钮，value默认为重置

  * submit：提交表单的按钮，value默认为提交

  * text：单行输入字段，可以输入文本

  * color：创建调色板

  ![](/assets/label_input_color.png)

  * date：选取日，月，年

  ![](/assets/label_input_date.png)

  * datetime：样式和text一样

    * value格式：YYYY-MM-DDThh：mm：ss：sZ\(Z：时区\)

  * datetime-local：选取年、月、日、时、分

    * value格式：YYYY-MM-DDThh：mm：ss：s\(.1秒\)

  ![](/assets/label_input_datetime_local.png)

  * email：样式和text一样，会自动渐染email域的值，手机端会唤出英文键盘

  * month：选取年、月

    * value格式：YYYY-MM

  ![](/assets/label_input_month.png)

  * number：数字，手机端会唤出数字键盘
    * 下面属性只对点击右侧按钮改变数字时有效，直接在输入框可以输入任何数字
    * max：允许的最大值
    * min：允许的最小值
    * step：每次点击时增加的数字
    * value：默认值

  ![](/assets/label_input_number.png)

  * range：一定范围内的数字
    * max：允许的最大值，默认为100
    * min：允许的最小值，默认为0
    * step：每次移动的间隔
    * value：默认值

  ![](/assets/label_input_range.png)

  * search：搜索框，输入后比text多一个x，点击后会删除所有输入的内容

  ![](/assets/label_input_search.png)

  * tel：电脑端和text样式一样，在手机端会唤出数字键盘

  * time：选取时、分

    * value格式：hh：mm：ss.s

  ![](/assets/label_input_time.png)

  * url：样式和text一样，会自动验证url的值

  * week：选取年、今年第几周

    * value格式：YYYY-W\(周数，从1到52\)

  ![](/assets/label_input_week.png)



