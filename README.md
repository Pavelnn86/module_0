# module_0
Итоговое задание по модулю 0. Улучшить программы по угадыванию числа. 

def game_core_v3(number):
    predict = 50
    count = 1
    if predict < number:
        predict += 25
        count += 1
        if predict < number:
            predict += 12
            count += 1
            if predict < number:
                predict += 7
            else:
                predict -= 6
        elif predict > number:
            predict -= 12
            count += 1
            if predict < number:
                predict += 7
            else:
                predict -= 6
    elif predict > number:
        predict -= 25
        count += 1
        if predict < number:
            predict += 12
            count += 1
            if predict < number:
                predict += 7
            else:
                predict -= 6
        elif predict > number:
            predict -= 12
            count += 1
            if predict < number:
                predict += 7
            else:
                predict -= 6
    while predict < number:
        predict += 1
        count += 1
    while predict > number:
        predict -= number
        count += 1
    return count
 
print(max(map(game_core_v3, range(1, 101))))
