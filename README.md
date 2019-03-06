# python


#def disp_temp(data):
 #   print("area:",data[0])
  #  for i in range(1,13):
   #     print("{:>2}:month average{:>.1f}\t".format(i, data[i]))
    #print("Year average:{}".format(data[13]))


def disp_area():
    i = 0
    for a in climate_data:
        print("{:>2}:{:<6}\t".format(i,a[0]), end="")
        i += 1
        if not (i % 5): print()
    print()


target_file = 'climate.txt'
with open(target_file, 'r', encoding='utf-8') as fp:
    raw_data = fp.readlines()

climate_data=[]
for item in raw_data:
    climate_data.append(item.rstrip('\n').split('\t'))

print(climate_data)


for i in range(len(climate_data)):
	print(climate_data[i][0])
print('----------------------------')

while True:
    disp_area()
    area = int(input("請輸入你要查詢平均溫度的地區：(-1結束)"))
    if area == -1: break
    disp_temp(climate_data[area])
    x = input("請按Enter鍵回主選單")
