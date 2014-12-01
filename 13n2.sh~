#!/bin/bash


echo "Программа, ктороя позволяет выяснить, были ли изменения в индексном дескрипторе файла"
echo "Разработана: Кузнецовой Ксенией"
echo
echo "Имя текущего катлога"

pwd
echo
answer="yes"
   
while [[ ! -e $file &&  $answer = "yes" ]]; do

if [ $answer = "yes" ]; then 
echo "Введите имя файла"
fi
read file
  echo
	if [ ! -e $file ]; then
	echo "Не существует такого файла. Продолжить? (yes/no)"
	read answer
	fi
if [ $answer = "no" ]; then
exit
fi

done

echo
echo "Введите год, месяц, число"
read year month day
yearf=$(stat -c %z $file | tr -s '-' ' ' | cut -d' ' -f1 )
monthf=$(stat -c %z $file | tr -s '-' ' ' | cut -d' ' -f2 )
dayf=$(stat -c %z $file | tr -s '-' ' ' | cut -d' ' -f3 )
echo
if [ $year -gt $yearf ]; then
echo "Изменения были"
exit 120
fi

if [ $yearf  -gt $year ]; then
echo "Изменений не было"
exit
fi

if [ $yearf  -eq $year ]; then 

	if [ $month -gt $monthf ]; then
	echo "Изменения были"
	exit 120
	fi
	
	if [ $month -lt $monthf ]; then
	echo "Изменений не было"
	exit
	fi

	if [ $month -eq $monthf ]; then 
		
		if [[  $day -lt $dayf || $day -eq $dayf ]]; then
		 echo "Изменений не было"
	        exit
                 fi
		
		if [ $day -gt $dayf ]; then
                echo "Изменения были "
                exit 120
                fi
	fi
fi

		


