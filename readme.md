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
	` git commit -m "wrote a readme file`

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
![Alt text](./pic/0.jpg)  

��Ϊָ��add distributed����  

![Alt text](./pic/1.jpg)

��ʾÿһ������
`git reflog`  

### �ܽ�
* HEADָ��İ汾���ǵ�ǰ�汾����ˣ�Git���������ڰ汾����ʷ֮�䴩��ʹ������git reset --hard commit_id��  
* ����ǰ����git log���Բ鿴�ύ��ʷ���Ա�ȷ��Ҫ���˵��ĸ��汾��
* Ҫ�ط�δ������git reflog�鿴������ʷ���Ա�ȷ��Ҫ�ص�δ�����ĸ��汾��

***

### ���������ݴ���

####��������Working Directory�����������ڵ������ܿ�����Ŀ¼�������ҵ�learngit�ļ��о���һ����������
![Alt text](./pic/2.jpg)  
#### �汾�� ��Repository������������һ������Ŀ¼��.git����������㹤����������Git�İ汾�⡣

Git�İ汾������˺ܶණ������������Ҫ�ľ��ǳ�Ϊstage�����߽�index�����ݴ���������GitΪ�����Զ������ĵ�һ����֧master���Լ�ָ��master��һ��ָ���HEAD��  

![Alt text](./pic/3.jpg)  

##### ǰ�潲�����ǰ��ļ���Git�汾������ӵ�ʱ���Ƿ�����ִ�еģ�

##### ��һ�����á�git add�����ļ���ӽ�ȥ��ʵ���Ͼ��ǰ��ļ��޸���ӵ��ݴ�����

##### �ڶ������á�git commit���ύ���ģ�ʵ���Ͼ��ǰ��ݴ��������������ύ����ǰ��֧��

##### ��Ϊ���Ǵ���Git�汾��ʱ��Git�Զ�Ϊ���Ǵ�����Ψһһ��master��֧�����ԣ����ڣ�commit������master��֧���ύ���ġ�

##### ����Լ����Ϊ����Ҫ�ύ���ļ��޸�ͨͨ�ŵ��ݴ�����Ȼ��һ�����ύ�ݴ����������޸ġ�

`Git is a distributed version control system. `  
`Git is free software distributed under the GPL.`  
`Git has a mutable index called stage.`  

##### Ȼ���ڹ���������һ��LICENSE�ı��ļ����������д����
##### ����git status�鿴һ��״̬��
* git status
* On branch master
* Changes not staged for commit:
* (use "git add <file>..." to update what will be committed> )
* (use "git checkout -- <file>..." to discard changes in > working directory)
*    modified:   readme.txt

* Untracked files:
* (use "git add <file>..." to include in what will be committed)

*    LICENSE
* no changes added to commit (use "git add" and/or "git commit -a")

#####  Git�ǳ�����ظ������ǣ�readme.txt���޸��ˣ���LICENSE������û�б���ӹ�����������״̬��Untracked��

##### ���ڣ�ʹ����������git add����readme.txt��LICENSE����Ӻ���git status�ٲ鿴һ�£�
 
 
*  git status
* On branch master
* Changes to be committed:
*   (use "git reset HEAD <file>..." to unstage)
 
*       new file:   LICENSE
*       modified:   readme.txt

##### ���ڣ��ݴ�����״̬�ͱ�������ˣ�
![Alt text](./pic/4.jpg)


### �ܽ�
##### �ݴ�����Git�ǳ���Ҫ�ĸ��Ū�������ݴ�������Ū������Git�ĺܶ�������׸���ʲô��

***
### �����޸�
ΪʲôGit�������汾����ϵͳ��Ƶ����㣬��ΪGit���ٲ���������޸ģ������ļ���  

ʲô���޸ģ�������������һ�У������һ���޸ģ�ɾ����һ�У�Ҳ��һ���޸ģ�������ĳЩ�ַ���Ҳ��һ���޸ģ�ɾ��һЩ�ּ���һЩ��Ҳ��һ���޸ģ���������һ�����ļ���Ҳ��һ���޸ġ�

##### Git��������޸ģ������á�git add��������ڹ������ĵ�һ���޸ı������ݴ�����׼���ύ�����ǣ��ڹ������ĵڶ����޸Ĳ�û�з����ݴ��������ԣ���git commit��ֻ������ݴ������޸��ύ�ˣ�Ҳ���ǵ�һ�ε��޸ı��ύ�ˣ��ڶ��ε��޸Ĳ��ᱻ�ύ��

### �ܽ�
##### �����Git����θ����޸ĵģ�ÿ���޸ģ������add���ݴ������ǾͲ�����뵽commit�С�

***
### �����޸�
`git checkout -- readme.txt`

����`git checkout -- readme.txt`����˼��,��readme.txt�ļ��ڹ��������޸�ȫ������,�������������:һ����readme.txt�޸ĺ�û�б��ŵ��ݴ���,���ڳ����޸ľͻص��Ͱ汾��һģһ����״̬;һ����readme.txt�Ѿ���ӵ��ݴ�����,�������޸�,���ڳ����޸ľͻص�����ݴ������״̬.��֮,����������ļ��ص����һ`git commit`����`git add`ʱ��״̬.


#####`git checkout -- file`��`--`����Ҫ,û��`--`�ͱ���˴���һ���·�֧������.


�����ļ�

> $ cat readme.txt  
Git is a distributed version control system.  
Git is free software distributed under the GPL.  
Git has a mutable index called stage.  
Git tracks changes of files.  
My stupid boss still prefers SVN.  

> $ git add readme.txt    

ʹ��`git status`�鿴,�޸�ֻ����ӵ����ݴ���,��û���ύ:  

> $ git status  
 On branch master  
 Changes to be committed:  
   (use "git reset HEAD <file>..." to unstage)  
       modified:   readme.txt  
no changes added to commit (use "git add" and/or "git commit -a")  

#####�����޸ĵĹ�����
> $ git checkout -- readme.txt

> $ git status
 On branch master
nothing to commit (working directory clean)

### �ܽ�
##### ����1:��������ĳ���������ļ�������,�붪�����������޸�ʱ,������`git checkout -- file`
##### ����2: �����������˹�����ĳ���ļ������ݣ�����ӵ����ݴ���ʱ���붪���޸ģ�����������һ��������git reset HEAD file���ͻص��˳���1���ڶ���������1������
##### ����3:�Ѿ��ύ�˲����ʵ��޸ĵ��汾��ʱ����Ҫ���������ύ���ο��汾����һ�ڣ�����ǰ����û�����͵�Զ�̿�.

***
### ɾ���ļ�
Git��,ɾ��Ҳ��һ���޸Ĳ���.���һ�����ļ�test.txt��Git���ύ.

> $ git add test.txt  

> $ git commit -m "add test.txt"

> [master 94cdc44] add test.txt

> 1 file changed, 1 insertion(+)

> create mode 100644 test.txt

��rm����ɾ��.
`rm test.txt`

Git֪��ɾ�����ļ�.��˹������Ͱ汾��Ͳ�һ����.`git status`�������ʾ��Щ�ļ���ɾ��.

> $ git status  
> *#* On branch master  
> *#* Changes not staged for commit:  
> *#*   (use "git add/rm <file>..." to update what will be   
> committed)  
> *#*   (use "git checkout -- <file>..." to discard changes > in working directory)  
> *#*  
> *#*       deleted:    test.txt  
> *#*  
> no changes added to commit (use "git add" and/or "git > commit -a")   

����������ѡ��.һ��1ȷʵ�Ӱ汾����ɾ�����ļ�,ʹ��`git rm`ɾ��,����`commit`

> *$* git rm test.txt  
> rm 'test.txt'  
> *$* git commit -m "remove test.txt"  
> [master d17efd8] remove test.txt  
> 1 file changed, 1 deletion(-)  
> delete mode 100644 test.txt  

��һ�������ɾ����.��Ϊ�汾���ﻹ��.���԰���ɾ�����ļ��ָ������°汾.  

`git checkout -- test.txt`

### �ܽ�
����git rm����ɾ��һ���ļ������һ���ļ��Ѿ����ύ���汾�⣬��ô����Զ���õ�����ɾ������ҪС�ģ���ֻ�ָܻ��ļ������°汾����ᶪʧ`���һ���ύ�����޸ĵ����ݡ�`
