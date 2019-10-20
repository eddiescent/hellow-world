# hellow-world
yo, this is Eddie.
Random number simulator:
import random
print(random.randit(0,9))

case 1:
import time,random

# 生成双方角色，并生成随机属性。
player_life = random.randint(100,150)
player_attack = random.randint(30,50)
enemy_life = random.randint(100,150)
enemy_attack = random.randint(30,50)

# 展示双方角色的属性
print('【玩家】\n'+'血量：'+str(player_life)+'\n攻击：'+str(player_attack))
print('------------------------')
time.sleep(1)
print('【敌人】\n'+'血量：'+str(enemy_life)+'\n攻击：'+str(enemy_attack))
print('------------------------')
time.sleep(1)

# 双方PK
while player_life > 0 and enemy_life > 0:
    player_life = player_life - enemy_attack
    enemy_life = enemy_life - player_attack
    print('你发起了攻击，【敌人】剩余血量'+str(enemy_life))
    print('敌人向你发起了攻击，【玩家】剩余血量'+str(player_life))
    print('-----------------------')
    time.sleep(1.5)

# 打印战果
if player_life > 0 and enemy_life <= 0:
    print('敌人死翘翘了，你赢了')
elif player_life <= 0 and enemy_life > 0:
    print('悲催，敌人把你干掉了！')
else:
    print('哎呀，你和敌人同归于尽了！')
    

BO5 case:
import time,random

player_victory = 0
enemy_victory = 0

for i in range(1,4):
    time.sleep(2)  # 让局与局之间有较明显的有时间间隔
    print(' \n——————现在是第'+str(i)+'局——————')  # 作为局的标记
 
    player_life = random.randint(100,150)
    player_attack = random.randint(30,50)
    enemy_life = random.randint(100,150)
    enemy_attack = random.randint(30,50)

    # 展示双方角色的属性
    print('【玩家】\n'+'血量：'+str(player_life)+'\n攻击：'+str(player_attack))
    print('------------------------')
    time.sleep(1)
    print('【敌人】\n'+'血量：'+str(enemy_life)+'\n攻击：'+str(enemy_attack))
    print('------------------------')
    time.sleep(1)

    # 双方PK
    while player_life > 0 and enemy_life > 0:
        player_life = player_life - enemy_attack
        enemy_life = enemy_life - player_attack
        print('你发起了攻击，【敌人】剩余血量'+str(enemy_life))
        print('敌人向你发起了攻击，【玩家】剩余血量'+str(player_life))
        print('-----------------------')
        time.sleep(1.5)

    #打印最终战果
    if player_life > 0 and enemy_life <= 0:
        player_victory += 1
        print('敌人死翘翘了，你赢了！')
    elif player_life <= 0 and enemy_life > 0:
        enemy_victory += 1
        print('悲催，敌人把你干掉了！')
    else:
        print('哎呀，你和敌人同归于尽了！')

if player_victory > enemy_victory :
    time.sleep(1)
    print('【最终结果：你赢了！】')
elif enemy_victory > player_victory:
    print('【最终结果：你输了！】')
else: 
    print('【最终结果：平局！】')

乘法口诀表:
for i in range(1,10):
    for j in range(1,i+1):
        print( '%d X %d = %d' % (j,i,i*j),end = '  ' )
    print('  ')
或:    
for i in range (1,10):
    for j in range(1,10):
        print('%d X %d = %d' % (j,i,i*j),end = '  ')
        if i==j:
            print('')
            break    
    

def my_len(words):
    counter = 0
    for i in words:
        counter = counter + 1
    return counter

a = '三根皮带，四斤大豆'
print(my_len(a))

def menu(appetizer, course):
    print('一份开胃菜：' + appetizer)
    print('一份主食：' + course)

menu('话梅花生','牛肉拉面')

def menu(appetizer, course, dessert = '绿豆沙'):
    print('一份开胃菜：' + appetizer)
    print('一份主食：' + course)
    print('一份甜品：' + dessert)


menu('话梅花生','牛肉拉面')
menu('话梅花生','牛肉拉面','银耳羹')
#银耳羹对应参数dessert



rent = 3000

def cost():
    utilities = int(input('请输入本月的水电费用'))
    food_cost = int(input('请输入本月的食材费用'))
    variable_cost = utilities + food_cost
    print('本月的变动成本是' + str(variable_cost))
    return variable_cost

def sum_cost():
    sum = rent + cost()
    print('本月的总成本是' + str(sum))

sum_cost()

#or method 2: global XXXXXX
rent = 3000

def cost():
    global variable_cost
    utilities = int(input('请输入本月的水电费用'))
    food_cost = int(input('请输入本月的食材费用'))
    variable_cost = utilities + food_cost
    print('本月的变动成本是' + str(variable_cost))

def sum_cost():
    sum = rent + variable_cost
    print('本月的总成本是' + str(sum))

cost()
sum_cost()



#Hellow kitty lottery:
import random
import time

# 用random函数在列表中随机抽奖，列表中只有3位候选者。

luckylist = ['海绵宝宝','派大星','章鱼哥']
# random模块中有个随机选取一个元素的方法：random.choice()。
a = random.choice(luckylist)  # 从3个人中随机选取1个人。
print('开奖倒计时',3)
time.sleep(1)  # 调用time模块，控制打印内容出现的时间
print('开奖倒计时',2)
time.sleep(1)
print('开奖倒计时',1)
time.sleep(1)
# 使用三引号打印hellokitty的头像
image = '''
 /\_)o<
|      \\
| O . O|
 \_____/
'''
print(image)  # ……
print('恭喜'+a+'中奖！')  # 使用print函数打印幸运者名单






import random
import time

# 将抽奖程序封装成函数
def choujiang(q,w,e):  # 定义一个抽奖函数，带有3个参数，也就是3位候选人
    luckylist = [q,w,e]  # 定义一个中奖名单的列表
    a = random.choice(luckylist)  # 在中奖名单里面随机选择
    print('开奖倒计时',3)
    time.sleep(1)
    print('开奖倒计时',2)
    time.sleep(1)
    print('开奖倒计时',1)
    time.sleep(1)
    image = '''
    /\_)o<
    |      \\
    | O . O|
    \_____/
    '''
    print(image)
    print('恭喜'+a+'中奖！')
    
choujiang('虚竹','萧峰','段誉')  # 调用函数


#项目3.0:
import math

def estimated(size=1,number=None,time=None):
    if (number == None) and (time != None):
        number = math.ceil(size * 80 / time)
        print('项目大小为%.1f个标准项目，如果需要在%.1f个工时完成，则需要人力数量为：%d人' %(size,time,number))  
    elif (number != None) and (time == None):
        time = size * 80 / number
        print('项目大小为%.1f个标准项目，使用%d个人力完成，则需要工时数量为：%.1f个' %(size,number,time))  

choice=input('请选择计算类型：（1-人力计算，2-工时计算）')
if choice=='1':
      size=float(input('请输入项目大小：（1代表标准大小，可以输入小数）'))
      number=None
      time=float(input('请输入工时数量：（请输入小数）'))
      estimated(size,number,time)
        
elif choice=='2':
      size=float(input('请输入项目大小：（1代表标准大小，可以输入小数）'))
      number=int(input('请输入人力数量：（请输入整数）'))
      time=None
        
  
  
  
  def div(num1, num2):
    growth = (num1 - num2) / num2
    percent = str(growth * 100) + '%'
    return percent

def warning():
    print('Error: 你确定上个月一毛钱都不赚不亏吗？')

def main():
    while True:
        num1 = float(input('请输入本月所获利润'))
        num2 = float(input('请输入上月所获利润'))
        if num2 == 0:
            warning()
            continue
        else:
            print('本月的利润增长率：' + div(num1,num2))
            break

main()



#剪刀石头布游戏：
import random

punches = ['石头','剪刀','布']
computer_choice = random.choice(punches)
user_choice = ''
user_choice = input('请出拳：（石头、剪刀、布）')
while user_choice not in punches:
    print('输入有误，请重新出拳')
    user_choice = input()
    
import random

# 出拳
punches = ['石头','剪刀','布']
computer_choice = random.choice(punches)
user_choice = ''
user_choice = input('请出拳：（石头、剪刀、布）')  # 请用户输入选择
while user_choice not in punches:  # 当用户输入错误，提示错误，重新输入
    print('输入有误，请重新出拳')
    user_choice = input()

# 亮拳
print('————战斗过程————')
print('电脑出了：%s' % computer_choice)
print('你出了：%s' % user_choice)

# 胜负
print('—————结果—————')
if user_choice == computer_choice:  # 使用if进行条件判断
    print('平局！')
elif (user_choice == '石头' and computer_choice == '剪刀') or (user_choice == '剪刀' and computer_choice == '布') or (user_choice == '布' and computer_choice == '石头'):
    print('你赢了！')
else:
    print('你输了！')


    
deposit = [100,300,900,2000,5000,0,2000,4500]

for i in range(1, len(deposit)):
    if deposit[i-1] == 0:  # 判断除数等于0时，特殊处理。
        print('你上次存款为 0 哦！')
    else:
        times = deposit[i]/deposit[i-1]
        print('你的存款涨了%f倍'%times)    


class Chinese:

    def __init__(self, name, birth, region):
        self.name = name   # self.name = '吴枫' 
        self.birth = birth  # self.birth = '广东'
        self.region = region  # self.region = '深圳'

    def born(self):
        print(self.name + '出生在' + self.birth)

    def live(self):
        print(self.name + '居住在' + self.region)    

person = Chinese('吴枫','广东','深圳') # 传入初始化方法的参数
person.born()
person.live()

class Chinese:
    def land_area(self,area):
        print('我们居住的地方，陆地面积是%d万平方公里左右。'% area)

class Cantonese(Chinese):
    # 直接对方法进行重写
    def land_area(self,area):
        print('我们居住的地方，陆地面积是%d万平方公里左右。'% int(area*0.0188))

gonger = Chinese()
yewen = Cantonese()
gonger.land_area(960)
yewen.land_area(960)

class Chinese:

    def land_area(self,area):
        print('我们居住的地方，陆地面积是%d万平方公里左右。' % area)

class Cantonese(Chinese):
    # 为参数 area 设置默认值。
    def land_area(self, area = 960, rate = 0.0188):
        Chinese.land_area(self, area * rate)

yewen = Cantonese()
yewen.land_area()
# 两个参数都有默认值，所以可以这么调用。


class Book:
    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state

    def show_info(self):
        if self.state == 0:
            status = '未借出'
        else:
            status = '已借出'
        return '名称：《%s》 作者：%s 推荐语：%s\n状态：%s ' % (self.name, self.author, self.comment, status)

book1 = Book('像自由一样美丽', '林达', '你要用光明来定义黑暗，用黑暗来定义光明')
# 传入参数，创建实例
print(book1.show_info())
#调用实例方法show_info()，打印出返回值

class BookManager

    def menu(self):
        print('欢迎使用流浪图书管理系统，每本沉默的好书都是一座流浪的岛屿，希望你有缘发现并着陆，为精神家园找到一片栖息地。\n')
        while True:
            print('1.查询所有书籍\n2.添加书籍\n3.借阅书籍\n4.归还书籍\n5.退出系统\n')
            choice = int(input('请输入数字选择对应的功能：'))
            if choice == 1:
                self.show_all_book()
                # 调用对象方法时self不能忘
            elif choice == 2:
                self.add_book()
            elif choice == 3:
                self.lend_book()
            elif choice == 4:
                self.return_book()
            elif choice == 5:
                print('感谢使用！愿你我成为爱书之人，在茫茫书海里相遇。')
                break


class Book:
 
    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state
 
    def __str__(self):
        status = '未借出'
        if self.state == 1:
            status = '已借出'
        return '名称：《%s》 作者：%s 推荐语：%s\n状态：%s ' % (self.name, self.author, self.comment, status)
 
class BookManager:

    books = []
    # 存储书籍的列表，每一个元素都是Book的实例对象
    def __init__(self):
        book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
        book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
        book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
        self.books.append(book1)
        self.books.append(book2)
        self.books.append(book3)

manager = BookManager()
print(len(manager.books))
# 打印列表长度
for book in manager.books:
    print(book)

class BookManager:

    books = []

    def __init__(self):
        book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
        book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
        book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
        self.books.append(book1)
        self.books.append(book2)
        self.books.append(book3)

    def menu(self):
        print('欢迎使用流浪图书管理系统，每本沉默的好书都是一座流浪的岛屿，希望你有缘发现并着陆，为精神家园找到一片栖息地。\n')
        while True:
            print('1.查询所有书籍\n2.添加书籍\n3.借出书籍\n4.归还书籍\n5.退出系统\n')
            choice = int(input('请输入数字选择对应的功能：'))
            if choice == 1:
                self.show_all_book()

    def show_all_book(self):
        for book in self.books:
        # self是实例对象的替身
            print(book)

manager = BookManager()
manager.menu()


class Book:
 
    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state
 
    def __str__(self):
        status = '未借出'
        if self.state == 1:
            status = '已借出'
        return '名称：《%s》 作者：%s 推荐语：%s\n状态：%s ' % (self.name, self.author, self.comment, status)
 
class BookManager:

    books = []

    def __init__(self):
        book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
        book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
        book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
        self.books.append(book1)
        self.books.append(book2)
        self.books.append(book3)

    def menu(self):
        print('欢迎使用流浪图书管理系统，每本沉默的好书都是一座流浪的岛屿，希望你有缘发现并着陆，为精神家园找到一片栖息地。\n')
        while True:
            print('1.查询所有书籍\n2.添加书籍\n3.借出书籍\n4.归还书籍\n5.退出系统\n')
            choice = int(input('请输入数字选择对应的功能：'))
            if choice == 1:
                self.show_all_book()
                break

    def show_all_book(self):
        for book in self.books:
            print(book)
            print('')

manager = BookManager()
manager.menu()


class Book:   

    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state

class BookManager:

    books = [] 

    def add_book(self):
        new_name = input('请输入书籍名称：')
        new_author =  input('请输入作者名称：')
        new_comment = input('请输入书籍推荐语：')
        # 获取书籍相应信息，赋值给属性

        new_book = Book(new_name, new_author, new_comment)
        # 传入参数，创建Book类实例new_book 
        self.books.append(new_book)
        # 将new_book添加到列表books里
        print('书籍录入成功！\n')

manager = BookManager()
manager.add_book()


class BookManager:

    books = []     
    def __init__(self):
        book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
        book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
        book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
        self.books.append(book1)
        self.books.append(book2)
        self.books.append(book3)

    def lend_book(self):
        borrow_name = input('请输入你想借阅的书籍名称：')
        for book in self.books:
        # 遍历列表，此时books有三个元素，即book1,book2,book3三个实例
            if book.name == borrow_name:
                # 如果列表中有实例的属性name和输入的书籍名称相等
                if book.state == 1:
                # 借阅状态为'已借出'
                    print('你来晚一步，这本书已经被借走了噢')
                    break
                    # 一旦有对象满足条件，则退出for循环
                else:
                # 借阅状态为'未借出'
                    print('借阅成功！借了不看会变胖噢～')
                    book.state = 1
                    break
            else:
                continue
          # 如果不满足book.name == borrow_name，则继续循环（这两行可以省略）  
        else:
            print('这本书暂时没有收录在系统里呢')

class Book:
 
    def __init__(self, name, author, comment, state = 0):
        self.name = name
        self.author = author
        self.comment = comment
        self.state = state
 
    def __str__(self):
        status = '未借出'
        if self.state == 1:
            status = '已借出'
        return '名称：《%s》 作者：%s 推荐语：%s\n状态：%s ' % (self.name, self.author, self.comment, status)
 
class BookManager:

    books = []
    def __init__(self):
        book1 = Book('惶然录','费尔南多·佩索阿','一个迷失方向且濒于崩溃的灵魂的自我启示，一首对默默无闻、失败、智慧、困难和沉默的赞美诗。')
        book2 = Book('以箭为翅','简媜','调和空灵文风与禅宗境界，刻画人间之缘起缘灭。像一条柔韧的绳子，情这个字，不知勒痛多少人的心肉。')
        book3 = Book('心是孤独的猎手','卡森·麦卡勒斯','我们渴望倾诉，却从未倾听。女孩、黑人、哑巴、醉鬼、鳏夫的孤独形态各异，却从未退场。',1)
        self.books.append(book1)
        self.books.append(book2)
        self.books.append(book3)
 
    def menu(self):
        print('欢迎使用流浪图书管理系统，每本沉默的好书都是一座流浪的岛屿，希望你有缘发现并着陆，为精神家园找到一片栖息地。\n')
        while True:
            print('1.查询所有书籍\n2.添加书籍\n3.借阅书籍\n4.归还书籍\n5.退出系统\n')
            choice = int(input('请输入数字选择对应的功能：'))
            if choice == 1:
                self.show_all_book()
            elif choice == 2:
                self.add_book()
            elif choice == 3:
                self.lend_book()
            elif choice == 4:
                self.return_book()
            elif choice == 5:
                print('感谢使用！愿你我成为爱书之人，在茫茫书海里相遇。')
                break
 
    def show_all_book(self):
        print('书籍信息如下：')
        for book in self.books:
            print(book)
            print('')

    def add_book(self):
        new_name = input('请输入书籍名称：')
        new_author =  input('请输入作者名称：')
        new_comment = input('请输入书籍推荐语：')
        new_book = Book(new_name, new_author, new_comment)
        self.books.append(new_book)
        print('书籍录入成功！\n')

    def check_book(self,name):
        for book in self.books:
            if book.name == name:
                 return book 
        else:
            return None

    def lend_book(self):
        name = input('请输入书籍的名称：')
        res = self.check_book(name)

        if res != None:
            if res.state == 1:
                print('你来晚了一步，这本书已经被借走了噢')
            else:
                print('借阅成功，借了不看会变胖噢～')
                res.state = 1
        else:
            print('这本书暂时没有收录在系统里呢')
    
    def return_book(self):
        name = input('请输入归还书籍的名称：')
        res = self.check_book(name)
        # 调用check_book方法，将返回值赋值给变量res
        if res == None:
        # 如果返回的是空值，即这本书的书名不在系统里
            print('没有这本书噢，你恐怕输错了书名～')
        else:
        # 如果返回的是实例对象
            if res.state == 0:
             # 如果实例属性state等于0，即这本书的借阅状态为'未借出'
                print('这本书没有被借走，在等待有缘人的垂青呢！')
            else:
             # 如果实例属性state等于1，即状态为'已借出'
                print('归还成功！')
                res.state = 0
                # 归还后书籍借阅状态为0，重置为'未借出'
 
manager = BookManager()
manager.menu()





