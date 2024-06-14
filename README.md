# 南華大學Python程式設計-二分法求平方根B-期末報告
11124208 王品雯 11124209 蔡岱伶

# 導入math庫以便使用math.sqrt函數
    import math 

    def sqrt_binary(n, epsilon):
# 初始區間設定為[0, n+0.25]
     low = 0
     high = n + 0.25
# 使用二分查找法求平方根
    while high - low > epsilon: 
        mid = (low + high) / 2  
 # 如果中點的平方與n的差值在精度範圍內，返回中點
    if abs(mid * mid - n) <= epsilon: 
         return mid
# 如果中點的平方小於n，移動下界
    elif mid * mid < n:  
         low = mid
# 如果中點的平方大於n，移動上界
    else:  
          high = mid
    
# 返回中點，作為近似的平方根
    return (low + high) / 2

# 讀取用戶輸入的字串，用戶輸入格式應為"n,epsilon"
    input_str = input("請輸入實數和計算精度： ")
# 將輸入字串以逗號為分隔符分割成兩個部分
    n_str, epsilon_str = input_str.split(',')
# 將分割出的字串轉換為浮點數
    n = float(n_str)

    epsilon = float(epsilon_str)
# 使用自定義的二分法函數計算平方根，並使用math庫的sqrt函數計算平方根
    sqrt_custom = sqrt_binary(n, epsilon) 

    sqrt_math = math.sqrt(n)
# 輸出結果，保留8位小數
    print(f"{sqrt_custom:.8f}")  

    print(f"{sqrt_math:.8f}")  
# 實作
![image]https://github.com/a738977498/python-report2/blob/main/4.png
