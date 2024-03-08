number=int(input("請輸入一個介於0到255的數字："));

def binary_hex_converter(number):
    
    #二進位轉換
    binary="";
    for i in range(7,-1,-1):
        if number>=(2**i):
            binary=binary+"1";
            number=number-(2**i);
        else:
            binary=binary+"0";
    print("二進位轉換為"+str(int(binary)));
    
    #十六進位轉換
    hexadecimal="";
    first_digit=binary[0:4];
    second_digit=binary[4:8];
    out_of_ten="ABCDEF";
    k=0;
    n=0;
    
    #第一位數
    for j in range(0,4,1):
        k=k+int(first_digit[j])*(2**(3-j));
    if k>=10:
        first_digit=out_of_ten[k-10];
    elif k==0:
        first_digit="";
    else:
        first_digit=str(k);
    
    #第二位數
    for m in range(0,4,1):
        n=n+int(second_digit[m])*(2**(3-m));
    if n>=10:
        second_digit=out_of_ten[n-10];
    else:
        second_digit=str(n);
    
    hexadecimal=first_digit+second_digit;
    return(hexadecimal);


if number>255 or number<0:
    print("The input should be a decimal number between 0~255");
else:
    print("十六進位轉換為"+binary_hex_converter(number));
