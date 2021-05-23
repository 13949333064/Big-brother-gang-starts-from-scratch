# Big-brother-gang-starts-from-scratch
# 从零开始学python
# 第一章：员工管理系统的创建

# 代码部分，如有错误部分，请大家给予斧正。
'''
需求：员工管理系统
功能：
1.添加员工信息
2.删除员工信息
3.修改员工信息
4.查看员工单个信息
5.查看所有员工信息
6.退出
'''

emps = []


def chocieFunc():  # 创建员工管理的页面
    print("*" * 30)
    print("1.添加员工信息")
    print("2.删除员工信息")
    print("3.修改员工信息")
    print("4.查看员工单个信息")
    print("5.查看所有员工信息")
    print("6.退出")
    print("*" * 30)


def addEmp():  # 创建员工信息页面
    id = input("请输入要添加的员工编号：")
    name = input("请输入要添加的员工姓名：")
    gender = input("请输入要添加的员工性别：")
    age = input("请输入要添加的员工年龄：")
    emp = {"id": id, "name": name, "gender": gender, "age": age}
    emps.append(emp)
    print("添加OK")


def delEmp():  # 创建删除员工信息的页面
    id = input("请输入要删除的员工编号：")
    for emp in emps:
        if emp.get("id") == id:
            # 将emp从emps中删除
            emps.remove(emp)
            print("删除OK")
            break
    else:
        print("请输入正确的编号：")


def updateEmp():  # 创建修改员工信息的页面
    id = input("请输入要修改的员工编号：")
    for emp in emps:
        if emp["id"] == id:
            emp["name"] = input("请输入修改后的员工编号：")
            emp["gender"] = input("请输入修改后的员工性别：")
            emp["age"] = input("请输入修改后的员工年龄：")
            # 因为emp是字典的形式，所以不推荐先删除后在添加，而是直接修改
            print("修改成功!!!")
            break
    else:
        print("查无此人!!!")


def getEmpById():  # 创建查看员工单个信息的页面
    id = input("请输入要查询的员工编号：")
    for emp in emps:
        if emp["id"] == id:
            print("编号\t姓名\t性别\t年龄")
            print(f"{emp['id']}\t{emp['name']}\t{emp['gender']}\t{emp['age']}")  # F 是格式化字符，用{}代表被替换掉的字符
            break
    else:
        print("查无此人!!!")


def getAllEmps():  # 创建查看所以员工个人信息的页面
    print("编号\t姓名\t性别\t年龄")
    for emp in emps:
        print(f"{emp['id']}\t{emp['name']}\t{emp['gender']}\t{emp['age']}")
    else:
        print(f"共查询到{len(emps)}条数据")


print("*****欢迎使用员工管理系统*****")
while True:
    chocieFunc()
    num = int(input("请输入指令："))
    if num == 1:
        addEmp()
    elif num == 2:
        delEmp()
    elif num == 3:
        updateEmp()
    elif num == 4:
        getEmpById()
    elif num == 5:
        getAllEmps()
    elif num == 6:
        print("欢迎下次再来!!!")
        break
    else:
        print("请输入正确的指令")
