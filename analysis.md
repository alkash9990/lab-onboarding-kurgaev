<img width="619" height="742" alt="Диаграмма без названия drawio (1)" src="https://github.com/user-attachments/assets/51e985d3-79a2-46b7-947a-fc240e156524" />
1. Код программы по схеме:
python


#def calc_bonus(x,y,z):
    #res=0
    #if x>1000:
        #for i in range(y):
            #if z==1:
                #res+=x*0.15
            #elif z==2:
                #res+=x*0.1
            #else:
                res+=x*0.05
    else:
        if y>10:
            res=x*y*0.02
        else:
            res=x*y*0.01
    return res


   
3. Анализ и оптимизация алгоритма:
В исходном алгоритме используется цикл for i in range(y) для многократного сложения. Это логически неэффективно, так как значения внутри цикла не меняются. Кроме того, это накладывает ограничение на переменную y (она обязана быть целым числом int, иначе range упадет с ошибкой изза возможного дробного ввода).
Для оптимизации циклическое сложение заменено на эквивалентное умножение, что упрощает вычисление, 

def calc_bonus_optimized(x, y, z):
    if y <= 0: 
        return 0
    if x > 1000:
        if z == 1:
            coef = 0.15
        elif z == 2:
            coef = 0.1
        else:
            coef = 0.05
    else:
        if y > 10:
            coef = 0.02
        else:
            coef = 0.01
    return x * y * coef
