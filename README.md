一、线性布局实现
新建布局文件：在 “res/layout” 目录下新建 XML 文件，命名为 “activity_linear.xml”，根布局设置为 LinearLayout，orientation 属性设为 “vertical”（垂直方向）。
编写布局代码：
垂直方向的 LinearLayout 内，添加 4 个水平方向的 LinearLayout，每个水平 LinearLayout 的 orientation 设为 “horizontal”；
每个水平 LinearLayout 内，添加 4 个 TextView，分别设置文本为 “One,One”“Two,One”“Three,One”“Four,One”、“One,Two”“Two,Two” 等；
为 TextView 设置统一样式：如 layout_width 设为 “0dp”、layout_weight 设为 “1”、textSize 设为 “16sp”、gravity 设为 “center”、margin 设为 “5dp”。
关联 Activity：在对应的 Activity中，通过 “setContentView (R.layout.activity_linear)” 加载该布局，运行模拟器查看效果。


二、表格布局实现
新建布局文件：在 “res/layout” 目录下新建 XML 文件，命名为 “activity_table.xml”，根布局设置为 TableLayout。
编写布局代码：
添加第一个 TableRow，内部放 1 个 TextView，文本设为 “Hello TableLayout”，textSize 设为 “20sp”，layout_column 设为 “0”，gravity 设为 “center”；
依次添加 6 个 TableRow，每个 TableRow 内放 2 个 TextView：
第一个 TextView：文本分别为 “Open...”“Save...”“Save As....”“Import...”“Export...”“Quit”，textSize 设为 “16sp”；
第二个 TextView：文本分别为 “Ctrl-O”“Ctrl-S”“Ctrl-Shift-s”“Ctrl-I”“Ctrl-E”，textSize 设为 “14sp”，textColor 设为 “#666666”，layout_gravity 设为 “end”；
为 TableLayout 设置 stretchColumns 属性为 “0”。
关联 Activity：在 Activity 中加载 “activity_table.xml”，运行模拟器查看。


三、约束布局实现
（一）约束布局 1（计算器界面）
新建布局文件：在 “res/layout” 目录下新建 XML 文件，命名为 “activity_constraint1.xml”，根布局设置为 ConstraintLayout。
编写布局代码：
添加 TextView（标题）：文本设为 “ConstraintLayoutTest”，textSize 设为 “22sp”，通过约束条件绑定到布局顶部中央（layout_constraintTop_toTopOf="parent"，layout_constraintStart_toStartOf="parent"，layout_constraintEnd_toEndOf="parent"）；
添加 TextView（输入显示）：文本设为 “0.0”，textSize 设为 “18sp”，background 设为 “#F5F5F5”，layout_width 设为 “match_parent”，layout_marginStart/End 设为 “20dp”，约束条件绑定到标题下方（layout_constraintTop_toBottomOf="@id / 标题 TextView 的 id"，marginTop 设为 “10dp”）；
添加按钮（数字 7、8、9 等）：共 12 个 Button（7、8、9、4、5、6、1、2、3、0，以及 “清除”“等于”，可选），每个按钮 textSize 设为 “18sp”，layout_width/layout_height 设为 “60dp”；
设置按钮约束：
“7” 按钮：约束到输入框下方左侧（layout_constraintTop_toBottomOf="@id / 输入 TextView 的 id"，layout_constraintStart_toStartOf="parent"，marginTop="10dp"，marginStart="20dp"）；
“8” 按钮：约束到 “7” 按钮右侧（layout_constraintStart_toEndOf="@id/7 按钮的 id"，layout_constraintTop_toTopOf="@id/7 按钮的 id"，marginStart="10dp"）；
“9” 按钮：约束到 “8” 按钮右侧（同理）；
后续行按钮（4、5、6；1、2、3；0）依次约束到上一行对应按钮下方，保持间距一致。


（二）约束布局 2（太空旅行界面）
资源准备：从课程群文件下载所需图片资源，将图片复制到 “res/drawable” 目录下。
新建布局文件：在 “res/layout” 目录下新建 XML 文件，命名为 “activity_constraint2.xml”，根布局设置为 ConstraintLayout。
编写布局代码：
添加 ImageView：设置 src 属性为群文件下载的图片（如 “@drawable/space_station”），layout_width 设为 “100dp”，layout_height 设为 “100dp”，约束到布局左上角（layout_constraintTop_toTopOf="parent"，layout_constraintStart_toStartOf="parent"，marginTop/Start 设为 “15dp”）；
添加 TextView（标题）：文本设为 “Space Stations”“Flights”，分别约束到 ImageView 右侧和下方，textSize 设为 “18sp”“16sp”；
添加 TextView（标识）：文本设为 “DCA”“MARS”，分别约束到布局中间左右两侧，textSize 设为 “16sp”，textStyle 设为 “bold”；
添加 TextView（选项）：文本设为 “One Way”“1 Traveller”，分别约束到布局中下部，textSize 设为 “14sp”；
添加 Button（DEPART）：文本设为 “DEPART”，textSize 设为 “16sp”，background 设为 “#2196F3”，textColor 设为 “white”，约束到布局底部中央（layout_constraintBottom_toBottomOf="parent"，layout_constraintStart_toStartOf="parent"，layout_constraintEnd_toEndOf="parent"，marginBottom 设为 “20dp”）；
调整各元素间距，确保界面整齐美观。
关联 Activity：在 Activity 中加载对应布局，运行模拟器查看效果。
