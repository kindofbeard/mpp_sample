sample_virvi2dfish2vo测试流程：
	该sample测试mpi_vi、mpi_ise、mpi_vo组件的绑定组合。创建mpi_vi、mpi_ise、mpi_vo，将它们绑定，再分别启动。mpi_vi采集两路图像，
传输给mpi_ise对两路鱼眼图像进行校正并拼接，直接传输给mpi_vo显示，到达测试时间后，分别停止运行并销毁。也可以手动按ctrl-c，终止测试。

读取测试参数的流程：
	sample提供了sample_virvi2dfish2vo.conf，测试参数都写在该文件中。
	启动sample_virvi2dfish2vo时，在命令行参数中给出sample_virvi2dfish2vo.conf的具体路径，sample_virvi2dfish2vo会读取sample_virvi2dfish2vo.conf，完成参数解析。
	然后按照参数运行测试。
从命令行启动sample_virvi2dfish2vo的指令：
	./sample_virvi2dfish2vo -path ./sample_virvi2dfish2vo.conf
	"-path ./sample_virvi2dfish2vo.conf"指定了测试参数配置文件的路径。

测试参数的说明：
1.auto_test_count：指定自动化测试次数
2.src_width：指定camera采集的图像宽度,由于VI模块硬件设计的原因,src_width必须是32的倍数
3.src_height：指定camera采集的图像高度
4.src_frame_rate：指定camera采集图像的帧率
5.ise_width：指定校正拼接后图像的宽度
6.ise_height：指定校正拼接后图像的高度
7.ise_stride：指定校正拼接后图像的stride值，该值必须是32的倍数
8.ise_flip_enable：指定是否使能图像翻转
9.ise_mirror_enable：指定是否使能图像镜像
10.display_width：指定显示宽度
11.display_height：指定显示高度
12.vo_test_duration：指定测试时间，0为循环显示，不退出sample_virvi2dfish2vo



