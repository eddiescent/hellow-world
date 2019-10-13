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
