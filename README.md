# moviedb


▼ 영화 검색, 예매율 구하는 법 (2개 중에 하나 선택)


```
# left join과 ifnull 쓰는 이유 => 예약이 없는 영화가 있다면 그냥 join을 하면 예약 없는 영화가 안 보임
# round(예매율,1) => 반올림하라, 소수점 1자리까지 보이게
select m.m_no, m_name, round((select count(*) from reservation where m_no=m.m_no)/(select count(*) from reservation)*100,1), m_startday, l_no from movie m;
select m.m_no, m_name, round(count(*)/(select count(*) from reservation)*100,1), m_startday, l_no from movie m left join reservation r on m.m_no=r.m_no group by m.m_no;
```
<br>
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
<br>
▼ 메인, 예약 건수 많은 순 10개, 예약 건수 같은 경우에는 영화번호순으로 정렬


```
select m.m_no, m_name from movie m left join reservation r on m.m_no=r.m_no group by m.m_no order by count(*) desc, m.m_no limit 10;
```
<br>
▼ 메인, 드래그


```
int xx=1;
```
```
all.addMouseMotionListener(new MouseMotionAdapter() {
  @Override
  public void mouseDragged(MouseEvent e) {
    // TODO Auto-generated method stub
    if (all.getX() - (xx - e.getX()) <= 1 && all.getX() - (xx - e.getX()) >= -850)
            {
      all.setLocation(all.getX()-(xx-e.getX()),10);
            }
    xx=e.getX();
  }
});
```
