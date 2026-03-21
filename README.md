# moviedb


▼ 영화 검색, 평점 구하는 법
```
# avg(re_star) => 리뷰테이블의 평점의 평균
# ifnull(평점평균,0) => 평점평균의 값이 null이면 0으로 대체하라
# left join과 ifnull 쓰는 이유 => 리뷰가 없는 영화가 있음. 그냥 join을 하면 리뷰 없는 영화가 안 보이고, ifnull을 안 쓰면 평점이 빈칸으로 나옴
# round(평점평균,1) => 반올림하라, 소수점 1자리까지 보이게
select m.m_no, m_name, round(ifnull(avg(re_star),0),1), m_startday, l_no from movie m left join review r on m.m_no=r.m_no group by m.m_no;
```

▼ 영화 정보, 영화 설명
```
JScrollPane jsp=new JScrollPane();
JTextArea tf1=new JTextArea();
```
```
// 원래 textarea는 textfield처럼 텍스트를 입력하는 것이기 때문에 수정이 불가하도록 setEditable(false) 사용
tf1.setEditable(false);
tf1.setText(bean.getA());
jsp.setViewportView(tf1);
```
