#### Pedometer - 计步器
辅助团队蓝牙室内定位项目实现的计步器

#### 原理
1. 波峰波谷的判定(连续上升、上升阀值等)
2. 峰谷差值需要大于峰谷阀值
3. 波峰时间差需要大于某个值
4. 峰谷差值是动态改变的

#### 可以调节的参数
1. 波峰判定中的连续上升次数lastContinueUpCount  2
2. 波峰判定中，没达到连续上升次数但可能是一次很大的上升值，判定该上升值的阀值  20
3. 波峰时间差判定  250ms
4. 计步累计启动步数  5
5. 参与峰谷阀值计算的阀值judgeValue  1.3
6. 重新计算峰谷阀值的峰谷差值累计个数arrayNum  4
7. 梯度化阀值中的梯度值和阀值设定averageValue()多判断了就尝试提高阀值，少判断了就尝试降低阀值测试走路、跑步、手机位置等多种场景，设定好不同场景的梯度，再设定阀值
