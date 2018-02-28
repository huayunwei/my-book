## Input

* name：input元素的名称，用于对提交到服务器后的表单数据进行标识

* type：规定input元素的类型\(图片为chrome下的显示\)

  * button：按钮，value属性的值为按钮上显示的文字

  * checkbox：多选按钮，同一组按钮name必须一致

  * file：用于文件的上传

    * 上传文件前

    ![](/assets/label_input_file_prev.png)

    * 上传文件后

    ![](/assets/label_input_file_next.png)

    * 支持accept和multiple属性

    ```markdown
    //accept属性，默认上传时选择的为全部类型的文件
    //accept中指定默认上传的类型，用逗号分割，在用户选择上传时可以手动修改类型上传，不会报错
    <input type="file" accept="image/gif,image/jpeg,image/jpg"></input>

    //multiple属性，默认上传时只能选择一个文件，添加后可以选择多个文件一起上传
    <input type="file" multiple>
    ```

  * hidden：隐藏不可见，但是数据仍然可以被提交

  * image：图片型提交按钮，src属性为图片地址，默认alt值为提交

  * password：密码框，和text外观一样，但是输入的内容不可见

    * 通过将input的type属性修改为text可以达到密码可见的效果

    ![](/assets/label_input_password.png)

  * radio：单选按钮，同一组按钮name必须一致

  * reset：创建重置表单的按钮，value默认为重置

  * submit：提交表单的按钮，value默认为提交

  * text：单行输入字段，可以输入文本

  * color：创建调色板

  ![](/assets/label_input_color.png)

  * date：选取日，月，年

  ![](/assets/label_input_date.png)

  * datetime：样式和text一样

  * datetime-local：选取年、月、日、时、分

  ![](/assets/label_input_datetime_local.png)

  * email：样式和text一样，会自动渐染email域的值，手机端会唤出英文键盘

  * month：选取年、月

  ![](/assets/label_input_month.png)

  * number：数字，手机端会唤出数字键盘

  ![](/assets/label_input_number.png)

  * range：一定范围内的数字

  ![](/assets/label_input_range.png)

  * search：搜索框，输入后比text多一个x，点击后会删除所有输入的内容

  ![](/assets/label_input_search.png)

  * tel：电脑端和text样式一样，在手机端会唤出数字键盘

  * time：选取时、分

  ![](/assets/label_input_time.png)

  * url：样式和text一样，会自动验证url的值

  * week：选取年、今年第几周

  ![](/assets/label_input_week.png)



