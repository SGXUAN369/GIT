（主要写一些我觉得好用且好记的方法）
零、先要下载torch和numpy安装包，并import它们
一、张量的创建
1.torch.tensor(data)
2.torch.ones()/torch.zeros()/torch.rand()
3.torch.ones_like(data)/torch.rand_like()/torch.zeros_like()
4.np_array = np.array(data)
x_np = torch.from_numpy(np_array)
二、打印张量的属性
x.shape  #形状
x.dtype  #数据类型
x.device #存储设备
三、索引和切片
1.x[0]   #取第一行
x[:,0]   #取第一列
x[:,-1]  #去最后一列

2.torch.narrow(input,dim,start,length)

四、形状变换
1.tensor.T                       #行列互换
2.torch.permute(input,dims)      #换维度
3.torch,squeeze(x,dim)           #挤掉指定维度的1，如果不填dim,就是挤掉所有维度的1
4.torch.unsqueeze(x,dim)         #在指定维度插入大小为1的新维度
5.torch.reshape(input,shape)     #将元素重新排列形状

五、拼接和运算
1.torch.cat(*tensor,dim)                 #拼接张量,dim=0,上下拼，dim=1,左右拼
2.y1=tensor@tensor.T
y2=tensor.matmul(tensor.T)
y3 = torch.rand_like(y1)
torch.matmul(tensor, tensor.T, out=y3)   #矩阵乘法的三种方式

3. z1=tensor * tensor
z2= tensor.mul(tensor)
z3 = torch.rand_like(tensor)
torch.mul(tensor, tensor, out=z3)        #元素逐个相乘的三种方式

六、其他
1.x.sum()                                #聚合操作
x.item()                                 #将单元素张量转为int或float
2.x.add_()                               #原地操作，将张量中个元素加上某个数
