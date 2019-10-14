# 循环链表

Reviewed: No
Status: 基础
频率: ⭐

[http://data.biancheng.net/view/8.html](http://data.biancheng.net/view/8.html)

# 双向链表(双向循环链表)的建立及C语言实现

之前接触到的[**链表**](http://data.biancheng.net/view/5.html)都只有一个指针，指向直接后继，整个[**链表**](http://data.biancheng.net/view/160.html)只能单方向从表头访问到表尾，这种结构的链表统称为 “单向链表”或“单链表”。

如果算法中需要频繁地找某结点的前趋结点，单链表的解决方式是遍历整个链表，增加算法的[**时间复杂度**](http://data.biancheng.net/view/2.html)，影响整体效率。

为了快速便捷地解决这类问题，在单向链表的基础上，给各个结点额外配备一个指针变量，用于指向每个结点的直接前趋元素。这样的链表被称为“[**双向链表**](http://data.biancheng.net/view/166.html)”或者“双链表”。

# 双链表中的结点

双向链表中的结点有两个指针域，一个指向直接前趋，一个指向直接后继。（链表中第一个结点的前趋结点为NULL，最后一个结点的后继结点为NULL）

![](http://data.biancheng.net/uploads/allimg/170718/2-1FGQ62RJT.png)

![](http://data.biancheng.net/uploads/allimg/170718/2-1FGQ62RJT.png)

[图](http://data.biancheng.net/view/200.html)1 双向链表中的结点

结点的具体构成：

    **typedef** **struct** line{ 
    	**struct** line * prior; //指向直接前趋 
    	int data; 
    	**struct** line * next; //指向直接后继
    }line;

# 创建双向链表并初始化

双向链表创建的过程中，每一个结点需要初始化数据域和两个指针域，一个指向直接前趋结点，另一个指向直接后继结点。例如，创建一个双向链表line（1，2，3）：

![](http://data.biancheng.net/uploads/allimg/170718/2-1FGQ62932M8.png)

图2 双向表（1，2，3）

实现代码：

    line* initLine(line * head){
        head=(line*)malloc(sizeof(line));//创建链表第一个结点（首元结点）
        head->prior=NULL;
        head->next=NULL;
        head->data=1;
        line * list=head;
        for (int i=2; i<=3; i++) {
            //创建并初始化一个新结点
            line * body=(line*)malloc(sizeof(line));
            body->prior=NULL;
            body->next=NULL;
            body->data=i;
           
            list->next=body;//直接前趋结点的next指针指向新结点
            body->prior=list;//新结点指向直接前趋结点
            list=list->next;
        }
        return head;
    }

# 双向链表中插入结点

比如在（1，2，3）中插入一个结点 4，变成（1，4，2，3）。实现效果图：

![](http://data.biancheng.net/uploads/allimg/170718/2-1FGQ6300c64.png)

图3 插入结点4

在双向链表中插入数据时，首先完成图 3 中标注为 1 的两步操作，然后完成标注为 2 的两步操作；反之，如果先完成 2，就无法通过头指针访问结点 2，需要额外增设指针，虽然能实现，但较前一种麻烦。

实现代码：

    line * insertLine(line * head,int data,int add){
        //新建数据域为data的结点
        line * temp=(line*)malloc(sizeof(line));
        temp->data=data;
        temp->prior=NULL;
        temp->next=NULL;
        //插入到链表头，要特殊考虑
        if (add==1) {
            temp->next=head;
            head->prior=temp;
            head=temp;
        }else{
            line * body=head;
            //找到要插入位置的前一个结点
            for (int i=1; i<add-1; i++) {
                body=body->next;
            }
            //判断条件为真，说明插入位置为链表尾
            if (body->next==NULL) {
                body->next=temp;
                temp->prior=body;
            }else{
                body->next->prior=temp;
                temp->next=body->next;
                body->next=temp;
                temp->prior=body;
            }
        }
        return head;
    }

# 双向链表中删除节点

双链表删除结点时，直接遍历链表，找到要删除的结点，然后利用该结点的两个指针域完成删除操作。例如，在（1，4，2，3）中删除结点 2：

    //删除结点的函数，data为要删除结点的数据域的值
    line * delLine(line * head,int data){
        line * temp=head;
        //遍历链表
        while (temp) {
            //判断当前结点中数据域和data是否相等，若相等，摘除该结点
            if (temp->data==data) {
                temp->prior->next=temp->next;
                temp->next->prior=temp->prior;
                free(temp);
                return head;
            }
            temp=temp->next;
        }
        printf("链表中无该数据元素");
        return head;
    }

# 双向链表中的查找和更改操作

双向链表的查找操作和单链表的实现方法完全一样，从链表的头结点或者首元结点开始遍历，这里不做过多解释。更改链表中某结点的数据域的操作是在查找的基础上完成的。通过遍历找到存储有该数据元素的结点后，直接更改其数据域就可以。