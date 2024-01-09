# 1.입력폼처리
- th:object는 오브젝트 정보를 넘겨주어야한다.
- th:field = "*{itemName}" 또는 (th:field = "${item.itemName}" id,name,value를 한번에 생성해줘 간편.

# 2.체크박스
<단일체크박스>
- 체크박스 미선택 후 전송 시 필드자체가 전송안됨.
- 해결방법 : 히든필드를 추가해 name="_open"처럼 기존체크박스앞에 '_'를 붙여 전송하면 스프링MVC는 체크를 해제했다고 인식해 open=false로 나타남.
<다중체크박스>
- @ModelAttribute : 반복해서 넣어주어야하는 데이터를  ModelAttribute를 사용하면 자동으로 담기게 된다.
````
    @ModelAttribute("regions")
    public Map<String, String> regions(){
        Map<String, String> regions = new LinkedHashMap<>();
        regions.put("SEOUL", "서울");
        regions.put("BUSAN", "부산");
        regions.put("JEJU", "제주");

        return regions;
    }
````
