# 8.6.2 stitch 명령어 작성 
 

![](../../_assets/8_6_4.png)<br>
*그림 8.6.4. 스티치 명령어 작성 예시*  


```stitch``` 명령어 입력
`[F6: 명령입력] - arcweld - 다음 - stitch` (on/off 선택 후 **[ENTER[YES]]** 버튼 클릭)


{% hint style="warning" %}
- ```S3 move L, spd=10mm/s, accu=3, tool=1```  
	 - L : 반드시 직선 보간을 선택  
	 - 10mm/s : 용접 속도, Stitch 용접의 ON 구간에서 속도, 반드시 단위를 mm/s로 선택
- ```arcon / arcoff``` 명령어 함께 사용 → 용접 
{% endhint %}