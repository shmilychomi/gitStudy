## Gitѧϰ�ʼ�

* �����汾��  
	`
	git init
	`
* ���ļ���ӵ��汾��  
	`
	git add readme.txt  
	`
* �ύ�ļ����ֿ�  
	`
	git commit -m "wrote a readme file
	`
#### �ܽ�
* ��ʼ��һ��Git�ֿ�,ʹ��git init����
* ����ļ���Git�ֿ�,������:
    ��һ��,ʹ��`git add`(�ɷ������ʹ��,��Ӷ���ļ�)
    �ڶ���,ʹ��`git commit`,���
	
***
	
* �鿴֮ǰ���޸�  
`
git diff readme.txt
`
### �ܽ�
* Ҫ��ʱ���չ�������״̬��ʹ��git status���
* ���git status���������ļ����޸Ĺ�����git diff���Բ鿴�޸����ݡ�

***

### �汾����  
�鿴��ʷ��¼  
`git log`

��ʽ�������Ϣ  
`git log --pretty=oneline`  

�˻ص���һ���汾  
`git rest --hard HEAD^`
(��Git��HEAD��ʾ��ǰ�汾,Ҳ�������µ��ύ,��һ���汾��HEAD^ ���ϸ��汾��HEAD^^)  

ָ���˻ص�ĳ���汾  
`git rest --hard 3628164` 3628164Ϊ�汾��

Git�İ汾�����ٶȷǳ��죬��ΪGit���ڲ��и�ָ��ǰ�汾��HEADָ�룬������˰汾��ʱ��Git�����ǰ�HEAD��ָ��append GPL����
![Alt text](./pic/0.png)  

��Ϊָ��add distributed����  

![Alt text](./pic/1.png)

��ʾÿһ������
`git reflog`  

### �ܽ�
* HEADָ��İ汾���ǵ�ǰ�汾����ˣ�Git���������ڰ汾����ʷ֮�䴩��ʹ������git reset --hard commit_id��  
* ����ǰ����git log���Բ鿴�ύ��ʷ���Ա�ȷ��Ҫ���˵��ĸ��汾��
* Ҫ�ط�δ������git reflog�鿴������ʷ���Ա�ȷ��Ҫ�ص�δ�����ĸ��汾��

***

