#

|数组|全局变量|意义
|:----:|:----:|:----:|
|**PLC_NC交换变量**|
|$A_DBB[0]|DB4900.DBX0.0|是否修整
|$A_DBB[1]|DB4900.DBX1.0|是否手动对刀
|$A_DBB[2]|DB4900.DBX2.0|是否退刀，异步动作信号
|$A_DBB[3]|DB4900.DBX3.0|液压动作回退到位
|$A_DBB[4]|DB4900.DBX4.0|液压动作伸出到位
|$A_DBB[5]|DB4900.DBX5.0|是否自动对刀
|$A_DBB[6]|DB4900.DBX6.0|C轴旋转
|$A_DBB[7]|DB4900.DBX7.0|自动对刀测量机构1汽缸回退到位
|$A_DBB[8]|DB4900.DBX8.0|自动对刀测量机构1汽缸伸出到位
|$A_DBB[9]|DB4900.DBX9.0|自动门打开开关
|$A_DBB[10]|DB4900.DBX10.0|自动门关闭开关
|$A_DBB[11]|DB4900.DBX11.0|
|$A_DBB[12]|DB4900.DBX12.0|砂轮当前状态(0停止/1启动)
|$A_DBB[13]|DB4900.DBX13.0|修整轮当前状态(0停止/1启动)
|$A_DBB[14]|DB4900.DBX14.0|升角夹紧动作检测信号(0未松开/1已松开)
|$A_DBB[15]|DB4900.DBX15.0|
|$A_DBB[16]|DB4900.DBX16.0|外圆砂轮当前状态(0停止/1启动)
|$A_DBB[17]|DB4900.DBX17.0|液压卡盘夹紧到位时为1，未到位为0
|$A_DBB[18]|DB4900.DBX18.0|液压卡盘松开到位时为1，未到位为0
|$A_DBB[19]|DB4900.DBX19.0|zc插补期间x退刀，同步动作信号
|$A_DBB[20]|DB4900.DBX20.0|自动对刀测量机构2汽缸回退到位
|$A_DBB[21]|DB4900.DBX21.0|自动对刀测量机构2汽缸伸出到位
|||与桁架机器人交互相关的信号
|$A_DBB[30]|DB4900.DBX30.0|机器人发给系统,取成品到位信号
|$A_DBB[31]|DB4900.DBX31.0|机器人发给系统,送毛坯到位信号
|$A_DBB[32]|DB4900.DBX32.0|机器人发给系统,手爪收回到位信号
|$A_DBB[60]|DB4900.DBX60.0|系统发给机器人,罩壳顶部门已打开信号,M80置1(有效),M81置0
|$A_DBB[61]|DB4900.DBX61.0|系统发给机器人,预完成,通知机械手准备,M82置1(有效),M83置0
|$A_DBB[62]|DB4900.DBX62.0|系统发给机器人,机床故障,M84置1(有效),M85置0
|$A_DBB[63]|DB4900.DBX63.0|系统发给机器人,卡盘松开完成,M86置1(有效),M87置0
|$A_DBB[64]|DB4900.DBX64.0|系统发给机器人,卡盘夹紧完成,M88置1(有效),M89置0
|||
|$A_PROBE[1]||测量探头1偏转
|$A_PROBE[2]||测量探头2偏转
|$AC_MEA[1]||测量探头1任务状态
|$AC_MEA[2]||测量探头2任务状态
||DB2700.DBX1.0|测头信号状态
|||
|MD14510[0]|DB4500.DBW0|润滑间歇时间(1min)
|MD14510[1]|DB4500.DBW2|润滑启动时间(10ms)
|MD14514[0]|DB4500.DBD2000|模拟量砂轮极限速度
|MD14510[4]|DB4500.DBW8|砂轮风扇停留时间
|||
|R299|-->WHEEL_RPM1|模拟量砂轮1转速
|R298|-->WHEEL_RPM2|模拟量砂轮2转速
|R297|-->DWHEEL_RPM1|模拟量修整轮1转速
|R296|-->DWHEEL_RPM2|模拟量修整轮2转速
|R280|-->$AA_IM[X]|退刀时存储X轴当前坐标
|R281|-->$AA_IM[Z]|退刀时存储Z轴当前坐标
|||
|PLCASUP1|ASUP1|PLC异步子程序-退刀键启动
|||
|**机床配置参数(CONFIG)**|
|CONFIG[0]||有无自动对刀0=无/1=有
|CONFIG[1]||有无自动门0=无/1=有
|CONFIG[2]||有无自动螺旋角0=无/1=有
|CONFIG[3]||砂轮类型选择(0模拟量/1伺服/2异步电机)
|CONFIG[4]||修整轮类型选择(0模拟量/1伺服2异步电机)
|CONFIG[5]||自动对刀后是否直接磨削(0否1是)
|CONFIG[6]||修整器结构类型 内螺纹时:0=成型轮向后修整,1=成型轮向前修整,2=X-Z插补修整;外螺纹时:0==成型轮V,1=成型轮Z,2=V-W插补修整,3=X-Z插补修整
|CONFIG[7]||螺旋退出工件0=否、1=是
|CONFIG[8]||外螺纹成型V与VW修整同时开放 0=否、1=是
|||

|**轴位置参数(POSITION)**|
|POSITION[0]||修整接触点坐标(双滚轮时为左侧滚轮)
|POSITION[1]||磨削接触点坐标
|POSITION[2]||装夹工件时X轴坐标
|POSITION[3]||装夹工件时Z轴坐标
|POSITION[4]||装夹工件时C轴坐标
|POSITION[5]||修整接触位置基准(砂轮主轴中心与滚轮圆弧顶部(金刚笔尖)重合时X(V)轴坐标)
|POSITION[6]||砂轮中心与滚轮中心水平重合时Z(W)轴坐标
|POSITION[7]||磨削接触位置基准(砂轮主轴中心与磨削初始接触位置重合时X轴的坐标)
|POSITION[8]||修整接触位置基准转存参数(当此参数与POSITION[5]不一致时,提醒用户需要重新对刀)
|POSITION[9]||工件左端
|POSITION[10]||工件右端
|POSITION[11]||磨削起点坐标
|POSITION[12]||磨削终点坐标
|POSITION[13]||手动对刀或者磨削过程中换头时X轴快速移动到安全位置(内螺纹为工件中心)
|POSITION[14]||磨削中点=(起点+终点)/2
|POSITION[15]||自动对刀Z轴起始安全位置
|POSITION[16]||自动对刀起始C轴角度
|POSITION[17]||自动对刀接近开关在工件中心时X轴坐标
|POSITION[18]||接近开关进入工件开始测量时的Z坐标
|POSITION[19]||接近开关能稳定感应到信号时的X轴坐标
|POSITION[20]||初始修整接触点坐标
|POSITION[21]||初始磨削接触点坐标
|POSITION[22]||未使用
|POSITION[23]||蜗杆修整垂直停靠点
|**磨削参数(GRIND)**|
|GRIND[0]||工件旋向(1=右旋/-1=左旋)
|GRIND[1]||工件头数
|GRIND[2]||工件模数(双导程蜗杆时为左齿)
|GRIND[3]||工件导程(双导程蜗杆时为左齿)
|GRIND[4]||工件螺距(双导程蜗杆时为左齿)
|GRIND[5]||是否自动计算螺旋角
|GRIND[6]||磨削长度
|GRIND[7]||磨削总角度
|GRIND[8]||度
|GRIND[9]||分
|GRIND[10]||秒
|GRIND[11]||0=批量磨削/1=单件调整
|GRIND[12]||偏刀调整(双齿面时为左齿面,头架向正向移动为正值，反之为负值)
|GRIND[13]||是否有锥度(0=无/1=有)
|GRIND[14]||锥度(工件右端为小头输入正值,反之负值))
|GRIND[15]||公制轴向模数/英制轴向模数/公制法向模数/英值法向模数/公制螺距/英制螺距
|GRIND[16]||锥度值GRIND[14]/2)
|GRIND[17]||锥度对应的X增量
|GRIND[18]||全长导程补偿
|GRIND[19]||中径调整
|GRIND[20]||工件中径
|GRIND[21]||是否自动计算螺旋升角(0=否/1=是)
|GRIND[22]||按键状态(1=修整键,2=手动对刀键,3自动对刀键)
|GRIND[23]||螺旋角度数
|GRIND[24]||双导程蜗杆右齿模数
|GRIND[25]||双导程蜗杆右齿右齿导程
|GRIND[26]||双导程蜗杆右齿右齿螺距
|GRIND[27]||0=正常磨削/1=双齿面
|GRIND[28]||是否X向磨削0=否/1=是
|GRIND[29]||是否Z向磨削0=否/1=是
|GRIND[30]||0=左齿面Z向磨削/1=右齿面Z向磨削/2=左右齿面Z向磨削
|GRIND[31]||右齿面偏刀调整
|||
|**修整参数(DRESSER)**|
|DRESSER[0]||新砂轮直径
|DRESSER[1]||砂轮当前直径
|DRESSER[2]||砂轮最大可用直径
|DRESSER[3]||砂轮最小可用直径
|DRESSER[4]||修整轮左右高度差(左侧为基准)
|DRESSER[5]||修整左侧砂轮时轮圆弧半径
|DRESSER[6]||修整右侧砂轮时轮圆弧半径
|DRESSER[7]||0=新砂轮/1=旧砂轮
|DRESSER[8]||修整轮直径
|DRESSER[9]||修整轮线速度
|DRESSER[10]||界面设定粗修次数
|DRESSER[11]||界面设定粗修进给
|DRESSER[12]||界面设定粗修速度
|DRESSER[13]||界面设定精修次数
|DRESSER[14]||界面设定精修进给
|DRESSER[15]||界面设定精修速度
|DRESSER[16]||界面设定修整停留时间
|DRESSER[17]||界面设定修整时砂轮线速度|界面设定修整时砂轮线速度
|DRESSER[18]||程序使用修整次数
|DRESSER[19]||程序使用修整进给
|DRESSER[20]||程序使用修整速度
|DRESSER[21]||程序使用修整时砂轮线速度
|DRESSER[22]||当前修整次数累计(用于修整次数控制)
|DRESSER[23]||当前修整次数累计(用于调整砂轮转速)
|DRESSER[24]||手动对出的新砂轮接触滚轮滚道时X轴坐标
|DRESSER[25]||修整时砂轮转速
|DRESSER[26]||观察参数(当前砂轮直径对应的修整接触点坐标)
|DRESSER[27]||齿型选择(0=三角形/1=梯形/2=双圆弧)
|DRESSER[28]||修整轮左右圆弧圆心间距
|DRESSER[29]||砂轮宽度
|DRESSER[30]||左侧滚轮圆弧半径调整
|DRESSER[31]||右侧滚轮圆弧半径调整
|DRESSER[32]||修左侧砂轮时滚轮圆弧中心与砂轮中心重合时Z(W)坐标
|DRESSER[33]||修右侧砂轮时滚轮圆弧中心与砂轮中心重合时Z(W)坐标
|DRESSER[34]||0=新砂轮时抬高半个砂轮宽度、1=新砂轮时左右偏移半个砂轮宽度
|DRESSER[35]||成型轮齿形高度(滚轮外圆到齿形圆弧顶部的高度)
|DRESSER[36]||手动对出的新砂轮接触滚轮外圆时X轴坐标
|DRESSER[37]||插补修整时抬到高度
|||
|**批量工艺界面参数(PROCESSER[0]-PROCESSER[99])**|
|PROCESSER[0]||粗磨单双(0=单/1=双)
|PROCESSER[1]||粗磨次数
|PROCESSER[2]||粗磨进
|PROCESSER[3]||粗磨头架转速
|PROCESSER[4]||粗磨修整设定
|PROCESSER[5]||粗磨磨削砂轮线速度
|PROCESSER[6]||粗磨修整次数
|PROCESSER[7]||粗磨修整进给
|PROCESSER[8]||粗磨修整速度
|PROCESSER[9]||粗磨修整砂轮线速度
|PROCESSER[10]||粗磨磨削砂轮转速
|PROCESSER[11]||粗磨修整砂轮转速
|PROCESSER[12]||Z向粗磨次数
|PROCESSER[13]||Z向粗磨进
|PROCESSER[14]||Z向粗磨头架转速
|PROCESSER[15]||Z向粗磨修整设定
|||
|PROCESSER[20]||半精磨单双
|PROCESSER[21]||半精磨次数
|PROCESSER[22]||半精磨进给
|PROCESSER[23]||半精磨头架转速
|PROCESSER[24]||半精磨修整设定
|PROCESSER[25]||半精磨磨削砂轮线速度
|PROCESSER[26]||半精磨修整次数
|PROCESSER[27]||半精磨修整进给
|PROCESSER[28]||半精磨修整速度
|PROCESSER[29]||半精磨修整砂轮线速度
|PROCESSER[30]||半精磨磨削砂轮转速
|PROCESSER[31]||半精磨修整砂轮转速
|PROCESSER[32]||Z向半精磨次数
|PROCESSER[33]||Z向半精磨进给
|PROCESSER[34]||Z向半精磨头架转速
|PROCESSER[35]||Z向半精磨修整设定
|||
|PROCESSER[40]||精磨单双
|PROCESSER[41]||精磨次数
|PROCESSER[42]||精磨进给
|PROCESSER[43]||精磨头架转速
|PROCESSER[44]||精磨修整设定
|PROCESSER[45]||精磨磨削砂轮线速度
|PROCESSER[46]||精磨修整次数
|PROCESSER[47]||精磨修整进给
|PROCESSER[48]||精磨修整速度
|PROCESSER[49]||精磨修整砂轮线速度
|PROCESSER[50]||精磨磨削砂轮转速
|PROCESSER[51]||精磨修整砂轮转速
|PROCESSER[52]||Z向精磨次数
|PROCESSER[53]||Z向精磨进给
|PROCESSER[54]||Z向精磨头架转速
|PROCESSER[55]||Z向精磨修整设定
|||
|PROCESSER[60]||终磨单双
|PROCESSER[61]||终磨次数
|PROCESSER[62]||终磨进给
|PROCESSER[63]||终磨头架转速
|PROCESSER[64]||终磨修整设定
|PROCESSER[65]||终磨磨削砂轮线速度
|PROCESSER[66]||终磨修整次数
|PROCESSER[67]||终磨修整进给
|PROCESSER[68]||终磨修整速度
|PROCESSER[69]||终磨修整砂轮线速度
|PROCESSER[70]||终磨磨削砂轮转速
|PROCESSER[71]||终磨修整砂轮转速
|PROCESSER[72]||Z向终磨次数
|PROCESSER[73]||Z向终磨进给
|PROCESSER[74]||Z向终磨头架转速
|PROCESSER[75]||Z向终磨修整设定
|||
|**当前工序参数(PROCESSER[100]-PROCESSER[119])**|
|PROCESSER[80]||当前工序单双(0=单/1=双)
|PROCESSER[81]||当前工序次数
|PROCESSER[82]||当前工序进给量
|PROCESSER[83]||当前工序头架转速
|PROCESSER[84]||当前工序修整设定
|PROCESSER[85]||当前工序磨削砂轮线速度
|PROCESSER[86]||当前工序修整次数
|PROCESSER[87]||当前工序修整进给
|PROCESSER[88]||当前工序修整速度
|PROCESSER[89]||当前工序修整砂轮线速度
|PROCESSER[90]||当前工序磨削砂轮转速
|PROCESSER[91]||当前工序修整砂轮转速
|||
|PROCESSER[100]||当前工序磨削次数(用于工序结束判断)
|PROCESSER[101]||当前工序磨削头数
|PROCESSER[102]||当前工序磨削次数(用于磨削中修整判断)
|PROCESSER[103]||用于标记是否进行过磨削中修整(0=否/1=是)
|PROCESSER[104]||当前工序(1=粗磨/2=半精磨/3=精磨/4=终磨)
|PROCESSER[105]||0=标准修整/1=自定义修整
|PROCESSER[106]||X向工艺磨削总量
|PROCESSER[107]||X向当前磨削总量
|PROCESSER[108]||磨削工件计数
|PROCESSER[109]||磨削几件后修砂轮
|PROCESSER[110]||工艺总修整量
|PROCESSER[111]||Z向工艺磨削总量
|PROCESSER[112]||Z向左齿面当前磨削总量
|PROCESSER[113]||Z向右齿面当前磨削总量
|||
|**调整工艺界面参数(PROCESSER[120]-PROCESSER[199])**|
|PROCESSER[120]||粗磨单双(1=单/2=双)
|PROCESSER[121]||粗磨次数
|PROCESSER[122]||粗磨进给
|PROCESSER[123]||粗磨头架转速
|PROCESSER[124]||粗磨修整设定
|PROCESSER[125]||粗磨磨削砂轮线速度
|PROCESSER[126]||粗磨修整次数
|PROCESSER[127]||粗磨修整进给
|PROCESSER[128]||粗磨修整速度
|PROCESSER[129]||粗磨修整砂轮线速度
|PROCESSER[130]||粗磨磨削砂轮转速
|PROCESSER[131]||粗磨修整砂轮转速
|PROCESSER[132]||Z向粗磨次数
|PROCESSER[133]||Z向粗磨进给
|PROCESSER[134]||Z向粗磨头架转速
|PROCESSER[135]||Z向粗磨修整设定
|||
|PROCESSER[140]||半精磨单双
|PROCESSER[141]||半精磨次数
|PROCESSER[142]||半精磨进给
|PROCESSER[143]||半精磨头架转速
|PROCESSER[144]||半精磨修整设定
|PROCESSER[145]||半精磨磨削砂轮线速度
|PROCESSER[146]||半精磨修整次数
|PROCESSER[147]||半精磨修整进给
|PROCESSER[148]||半精磨修整速度
|PROCESSER[149]||半精磨修整砂轮线速度
|PROCESSER[150]||半精磨磨削砂轮转速
|PROCESSER[151]||半精磨修整砂轮转速
|PROCESSER[152]||Z向半精磨次数
|PROCESSER[153]||Z向半精磨进给
|PROCESSER[154]||Z向半精磨头架转速
|PROCESSER[155]||Z向半精磨修整设定
|||
|PROCESSER[160]||精磨单双
|PROCESSER[161]||精磨次数
|PROCESSER[162]||精磨进给
|PROCESSER[163]||精磨头架转速
|PROCESSER[164]||精磨修整设定
|PROCESSER[165]||精磨磨削砂轮线速度
|PROCESSER[166]||精磨修整次数
|PROCESSER[167]||精磨修整进给
|PROCESSER[168]||精磨修整速度
|PROCESSER[169]||精磨修整砂轮线速度
|PROCESSER[170]||精磨磨削砂轮转速
|PROCESSER[171]||精磨修整砂轮转速
|PROCESSER[172]||Z向精磨次数
|PROCESSER[173]||Z向精磨进给
|PROCESSER[174]||Z向精磨头架转速
|PROCESSER[175]||Z向精磨修整设定
|||
|PROCESSER[180]||终磨单双
|PROCESSER[181]||终磨次数
|PROCESSER[182]||终磨进给
|PROCESSER[183]||终磨头架转速
|PROCESSER[184]||终磨修整设定
|PROCESSER[185]||终磨磨削砂轮线速度
|PROCESSER[186]||终磨修整次数
|PROCESSER[187]||终磨修整进给
|PROCESSER[188]||终磨修整速度
|PROCESSER[189]||终磨修整砂轮线速度
|PROCESSER[190]||终磨磨削砂轮转速
|PROCESSER[191]||终磨修整砂轮转速
|PROCESSER[192]||Z向终磨次数
|PROCESSER[193]||Z向终磨进给
|PROCESSER[194]||Z向终磨头架转速
|PROCESSER[195]||Z向终磨修整设定
|**对刀参数(TOOL_SET)**|
|TOOL_SET[0]||磨削起始角度(双导程蜗杆时为左齿面磨削时C轴起始角度)
|TOOL_SET[1]||自动对刀调整(头架向正向移动为正值，反之为负值)
|TOOL_SET[2]||对刀开始时读取C轴初始角度
|TOOL_SET[3]||对刀开始时读取Z轴初始坐标
|TOOL_SET[4]||手动对刀模式(zc插补0/静止对刀1)
|TOOL_SET[5]||首件对刀(0=否/1=是)
|TOOL_SET[6]||内螺纹测头中心(接近开关感应片中心)与砂轮中心Z向间距
|TOOL_SET[7]||内螺纹自动对刀接近开关伸出时Z轴坐
|TOOL_SET[8]||内螺纹自动对刀开关测量方式下，开关进入工件开始测量Z起始位置
|TOOL_SET[9]||自动对刀C轴起始角
|TOOL_SET[10]||接近开关在工件中心时X轴坐标
|TOOL_SET[11]||接近开关感应到信号时X轴坐标
|TOOL_SET[12]||外螺纹(0=起点对刀/1=中点对刀)
|TOOL_SET[13]||探头伸出后碰到工件外圆时X轴机械坐标
|TOOL_SET[14]||测头触碰右端面时Z轴坐标
|TOOL_SET[15]||探头半径
|TOOL_SET[20]||工件右端面到反相器孔的距离
|TOOL_SET[21]||右齿面磨削起始角度
|TOOL_SET[22]||0=左齿面对刀/1=右齿面对刀
|TOOL_SET[23]||外螺纹时侧头中心(接近开关感应片中心)与砂轮中心重合时Z轴坐标
|TOOL_SET[24]||需执行异步子程序计算标记0=不计算/1=计算
|TOOL_SET[25]||蜗杆手动确定探头触碰端面时X轴坐标
|TOOL_SET[26]||蜗杆手动确定探头触碰端面时Z轴坐标
|TOOL_SET[27]||蜗杆探头自动检测到端面时Z轴坐标
|TOOL_SET[28]||蜗杆探头自动检测到端面时Z轴坐标(参考参数,首件工件对刀结束后将TOOL_SET[27]数据写入TOOL_SET[28])
|TOOL_SET[29]||是否测量端面0=否、1=是
|TOOL_SET[30]||接近开关感应圆片中心-测头间距

|**梯形(TRAP)**|
|TRAP[0]||齿高
|TRAP[1]||齿根宽
|TRAP[2]||左齿形角
|TRAP[3]||右齿形角
|TRAP[4]||左齿根圆弧半径
|TRAP[5]||右齿根圆弧半径
|TRAP[6]||左齿顶过渡圆弧半径
|TRAP[7]||右齿顶过渡圆弧半径
|TRAP[8]||调整左角
|TRAP[9]||调整右角
|TRAP[10]||当前左角
|TRAP[11]||当前右角
|TRAP[12]||拉出斜线与水平线夹角
|TRAP[13]||左齿根圆弧半径调整
|TRAP[14]||右齿根圆弧半径调整
|TRAP[15]||当前左齿根圆弧半径
|TRAP[16]||当前右齿根圆弧半径
|TRAP[17]||左齿顶过渡圆弧半径调整
|TRAP[18]||右齿顶过渡圆弧半径调整
|TRAP[19]||当前左齿顶过渡圆弧半径
|TRAP[20]|当前右齿顶过渡圆弧半径
|||
|**双圆弧(DARC)**||
|DARC[0]||齿高
|DARC[1]||外圆直径
|DARC[2]||球中心直径
|DARC[3]||钢球直径
|DARC[4]||接触角
|DARC[5]||初始滚道左半径
|DARC[6]||初始滚道右半径
|DARC[7]||调整滚道左半径
|DARC[8]||调整滚道右半径
|DARC[9]||当前滚道左半径
|DARC[10]||当前滚道右半径
|DARC[11]||过渡圆弧半径
|DARC[12]||当前滚道左半径水平偏心
|DARC[13]||当前滚道右半径水平偏心
|DARC[14]||当前滚道左半径垂直偏心
|DARC[15]||当前滚道右半径垂直偏心
|DARC[16]||滚道左半径水平偏心调整
|DARC[17]||滚道右半径水平偏心调整
|DARC[18]||滚道左半径垂直偏心调整
|DARC[19]||滚道右半径垂直偏心调整
|DARC[20]||滚道左半径水平偏心
|DARC[21]||滚道右半径水平偏心
|DARC[22]||滚道左半径垂直偏心
|DARC[23]||滚道右半径垂直偏心
|||
|**蜗杆用R参数**||
|R3|修整次数||
|R7|当前V轴修整位置|
|R8|砂轮宽度|
|R9|当前砂轮直径|
|R10|修整轮中心间距|L=W左-W右+B+r1+r2|
|R11|左修整轮比右修整轮高出的举例|
|R12|修整轮电主轴转速|
|R13|电主轴启动延时|
|R14|双滚轮间距的中心和砂轮中心重合时的W坐标|W=(W左+W右)/2	W方向修整中心|
|R15|修整轮圆弧中心和砂轮中心在V方向重合时的V坐标|砂轮中心V坐标|
|R16|修整结束水平轴停泊点|
|R17|修整结束垂直轴停泊点|
|R29|修整轮圆弧半径,生成蜗杆程序时确定,此处变量只检验|
|修整参数||
|R18|粗修进给速度|
|R19|精修进给速度|
|R20|粗修进给量|
|R21|精修进给量|
|R22|修整定位速度|
|R23|修整返回速度|
||不需要修改的参数||
|R28|修整偏移距离|
|R25|当前修整次数|
|R26|当前修整进给速度|
|R27|当前修整进给量|
|||



