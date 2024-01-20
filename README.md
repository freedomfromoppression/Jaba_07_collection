# Jaba_07_collection
package ch08_collection;

import java.lang.StackWalker.Option;
import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;
import java.util.Comparator;
import java.util.Scanner;



public class PlayList {

	public static void main(String[] args) {
		ArrayList<String> playList = new ArrayList<>(Arrays.asList("Perfect Night:LE SSERAFIM (르세라핌)",
				"To. X:태연 (TAEYEON)", "Drama:aespa", "사랑은 늘 도망가:임영웅", "첫 눈:EXO", "헤어지자 말해요:박재정", "인사:범진", "에피소드:이무진",
				"Do or Die:임영웅", "모래 알갱이:임영웅", "Seven (feat. Latto) - Clean Ver.:정국", "우리들의 블루스:임영웅",
				"그대만 있다면 (여름날 우리 X 너드커넥션 (Nerd Connection)):너드커넥션 (Nerd Connection)", "Baddie:IVE (아이브)",
				"다시 만날 수 있을까:임영웅", "이제 나만 믿어요:임영웅", "무지개:임영웅", "London Boy:임영웅", "아버지:임영웅", "Polaroid:임영웅",
				"Love Lee:AKMU (악뮤)", "I AM:IVE (아이브)", "You & Me:제니 (JENNIE)", "인생찬가:임영웅", "A bientot:임영웅",
				"Love 119:RIIZE", "Standing Next to You:정국", "연애편지:임영웅", "Get A Guitar:RIIZE", "후라이의 꿈:AKMU (악뮤)",
				"Super Shy:NewJeans", "너의 모든 순간:성시경", "사막에서 꽃을 피우듯:우디 (Woody)", "Ditto:NewJeans",
				"잘 지내자, 우리 (여름날 우리 X 로이킴):로이킴", "ETA:NewJeans", "Hype Boy:NewJeans", "퀸카 (Queencard):(여자)아이들",
				"별 떨어진다 (I Do):디오 (D.O.)", "어떻게 이별까지 사랑하겠어, 널 사랑하는 거지:AKMU (악뮤)", "사랑할 수밖에:볼빨간사춘기", "Discord:QWER",
				"Either Way:IVE (아이브)", "Smoke (Prod. Dynamicduo, Padi):다이나믹 듀오", "사랑인가 봐:멜로망스", "Dynamite:방탄소년단",
				"봄날:방탄소년단", "Off The Record:IVE (아이브)", "Merry PLLIstmas:PLAVE", "MANIAC:VIVIZ (비비지)", "Spicy:aespa",
				"사건의 지평선:윤하 (YOUNHA)", "Fast Forward:전소미", "사랑하지 않아서 그랬어:임한별", "음악의 신:세븐틴 (SEVENTEEN)",
				"그대가 내 안에 박혔다(그내박):순순희(기태)", "잠시라도 우리:성시경", "Kitsch:IVE (아이브)", "OMG:NewJeans", "취중고백:김민석",
				"이브, 프시케 그리고 푸른 수염의 아내:LE SSERAFIM (르세라핌)", "Steal The Show (From “엘리멘탈”):Lauv", "LOVE DIVE:IVE (아이브)",
				"Butter:방탄소년단", "심(心):DK(디셈버)", "파이팅 해야지 (Feat. 이영지):부석순 (SEVENTEEN)", "눈이 오잖아(Feat.헤이즈):이무진",
				"여섯 번째 여름:PLAVE", "그중에 그대를 만나:김호중", "물론:허각", "After LIKE:IVE (아이브)",
				"모든 날, 모든 순간 (Every day, Every Moment):폴킴", "I Don't Think That I Like Her:Charlie Puth",
				"Chill Kill:Red Velvet (레드벨벳)", "주저하는 연인들을 위해:잔나비", "Bubble:STAYC(스테이씨)", "손오공:세븐틴 (SEVENTEEN)",
				"해요 (2022):#안녕", "예뻤어:DAY6 (데이식스)", "I Love You:안세하", "화이트 (White):폴킴", "다정히 내 이름을 부르면:경서예지",
				"그대가 있는 곳, 언제 어디든:로이킴", "사랑..그게 뭔데:지아", "Dangerously:Charlie Puth", "GODS:NewJeans",
				"Attention:NewJeans", "UNFORGIVEN (feat. Nile Rodgers):LE SSERAFIM (르세라핌)", "한 페이지가 될 수 있게:DAY6 (데이식스)",
				"나에게 그대만이:탑현", "Dear. PLLI:PLAVE", "Closer Than This:지민", "3D (feat. Jack Harlow):정국",
				"I Love My Body:화사 (HWASA)", "기다릴게:PLAVE", "Yes or No:정국", "Snowman:Sia",
				"편지 한 장 (부제: 서른에 만난 첫 세상) (A letter):김호중", "I Just Love Ya:PLA"));
		for (String a : playList) {
			System.out.println(a);
		}
		System.out.println("=============== 정렬");
		// default 오름차순
		// ABC > abc > 가나다 순으로 정렬
		Collections.sort(playList);
		System.out.println(playList);
		System.out.println("=========== 내림차순 정렬");
		Collections.sort(playList, Comparator.reverseOrder());
		System.out.println(playList);
		ArrayList<String> searchList = searchSong("가수", "임영웅", playList);
		System.out.println(searchList);
		System.out.println(searchList.size());
	
		ArrayList<String> searchList2 = searchSong("제목", "사랑", playList);
		System.out.println(searchList2);
		System.out.println(searchList2.size());
		
		//사용자에게 1. 가수 or 제목을 입력받고
		//       2. 검색 키워드를 입력받아
		//       3. 순위와 노래제목.가수 를 순서대로 출력하시오(한줄한줄)
        //       4. 없으면 ........... 아쉽지만 검색 결과가 없습니다..(출력)
		Scanner scan = new Scanner(System.in);
		while(true) {
			
		}
	
	
	
	
	}

	// input : 1.가수 or 2.노래 2.키워드, 3.리스트
	// output: 리스트
	public static ArrayList<String> searchSong(String option, String keyword, ArrayList<String> arr) {
		ArrayList<String> result = new ArrayList<>();
		for (int i = 0; i < arr.size(); i++) {
			// : 을 기준으로 자르기 0 제목, 1 가수
			String[] temp = arr.get(i).split(":");
			if (option.equals("가수")) {
				if (temp[1].contains(keyword)) {
					result.add(arr.get(i));
				}
			} else if (option.equals("제목")) {
				if (temp[0].contains(keyword)) {
					result.add(arr.get(i));
				}
			}
		}
		return result;

	}
}

package ch08_collection;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.HashMap;
import java.util.HashSet;

public class PalyListMap {

	public static void main(String[] args) {
		ArrayList<String> playList = new ArrayList<>(Arrays.asList("Perfect Night:LE SSERAFIM (르세라핌)",
				"To. X:태연 (TAEYEON)", "Drama:aespa", "사랑은 늘 도망가:임영웅", "첫 눈:EXO", "헤어지자 말해요:박재정", "인사:범진", "에피소드:이무진",
				"Do or Die:임영웅", "모래 알갱이:임영웅", "Seven (feat. Latto) - Clean Ver.:정국", "우리들의 블루스:임영웅",
				"그대만 있다면 (여름날 우리 X 너드커넥션 (Nerd Connection)):너드커넥션 (Nerd Connection)", "Baddie:IVE (아이브)",
				"다시 만날 수 있을까:임영웅", "이제 나만 믿어요:임영웅", "무지개:임영웅", "London Boy:임영웅", "아버지:임영웅", "Polaroid:임영웅",
				"Love Lee:AKMU (악뮤)", "I AM:IVE (아이브)", "You & Me:제니 (JENNIE)", "인생찬가:임영웅", "A bientot:임영웅",
				"Love 119:RIIZE", "Standing Next to You:정국", "연애편지:임영웅", "Get A Guitar:RIIZE", "후라이의 꿈:AKMU (악뮤)",
				"Super Shy:NewJeans", "너의 모든 순간:성시경", "사막에서 꽃을 피우듯:우디 (Woody)", "Ditto:NewJeans",
				"잘 지내자, 우리 (여름날 우리 X 로이킴):로이킴", "ETA:NewJeans", "Hype Boy:NewJeans", "퀸카 (Queencard):(여자)아이들",
				"별 떨어진다 (I Do):디오 (D.O.)", "어떻게 이별까지 사랑하겠어, 널 사랑하는 거지:AKMU (악뮤)", "사랑할 수밖에:볼빨간사춘기", "Discord:QWER",
				"Either Way:IVE (아이브)", "Smoke (Prod. Dynamicduo, Padi):다이나믹 듀오", "사랑인가 봐:멜로망스", "Dynamite:방탄소년단",
				"봄날:방탄소년단", "Off The Record:IVE (아이브)", "Merry PLLIstmas:PLAVE", "MANIAC:VIVIZ (비비지)", "Spicy:aespa",
				"사건의 지평선:윤하 (YOUNHA)", "Fast Forward:전소미", "사랑하지 않아서 그랬어:임한별", "음악의 신:세븐틴 (SEVENTEEN)",
				"그대가 내 안에 박혔다(그내박):순순희(기태)", "잠시라도 우리:성시경", "Kitsch:IVE (아이브)", "OMG:NewJeans", "취중고백:김민석",
				"이브, 프시케 그리고 푸른 수염의 아내:LE SSERAFIM (르세라핌)", "Steal The Show (From “엘리멘탈”):Lauv", "LOVE DIVE:IVE (아이브)",
				"Butter:방탄소년단", "심(心):DK(디셈버)", "파이팅 해야지 (Feat. 이영지):부석순 (SEVENTEEN)", "눈이 오잖아(Feat.헤이즈):이무진",
				"여섯 번째 여름:PLAVE", "그중에 그대를 만나:김호중", "물론:허각", "After LIKE:IVE (아이브)",
				"모든 날, 모든 순간 (Every day, Every Moment):폴킴", "I Don't Think That I Like Her:Charlie Puth",
				"Chill Kill:Red Velvet (레드벨벳)", "주저하는 연인들을 위해:잔나비", "Bubble:STAYC(스테이씨)", "손오공:세븐틴 (SEVENTEEN)",
				"해요 (2022):#안녕", "예뻤어:DAY6 (데이식스)", "I Love You:안세하", "화이트 (White):폴킴", "다정히 내 이름을 부르면:경서예지",
				"그대가 있는 곳, 언제 어디든:로이킴", "사랑..그게 뭔데:지아", "Dangerously:Charlie Puth", "GODS:NewJeans",
				"Attention:NewJeans", "UNFORGIVEN (feat. Nile Rodgers):LE SSERAFIM (르세라핌)", "한 페이지가 될 수 있게:DAY6 (데이식스)",
				"나에게 그대만이:탑현", "Dear. PLLI:PLAVE", "Closer Than This:지민", "3D (feat. Jack Harlow):정국",
				"I Love My Body:화사 (HWASA)", "기다릴게:PLAVE", "Yes or No:정국", "Snowman:Sia",
				"편지 한 장 (부제: 서른에 만난 첫 세상) (A letter):김호중", "I Just Love Ya:PLA"));

		//전체 가수들의 노래 리스트를 만들려면?
		//1. 가수목록생성(유니크하게)
		HashSet<String> singer = new HashSet<>();
		for(int i=0; i< playList.size(); i++) {
			String[]temp = playList.get(i).split(":");
			singer.add(temp[1]);
			}
		System.out.println(singer.size() + ":" + singer);
		HashMap<String, ArrayList<String>> singerMap = new HashMap<>();
		for(String sing : singer) {
			singerMap.put(sing,  makeSongList(sing,playList));
		}
		System.out.println(singerMap);
	}
	public static ArrayList<String> makeSongList(String nm, ArrayList<String>arr){
		ArrayList<String> result = new ArrayList<>();
		for(int i=0; i< arr.size(); i++ ) {
			String[]temp = arr.get(i).split(":");
			//입력받은 가수와 같으면 담기
			if(nm.equals(temp[1])){
				result.add(temp[0]);
				
			}
		}
		return result;
	}

}

package ch08_collection;



import java.util.HashSet;



public class LottoMain {



	public static void main(String[] args) {

		

		//user 희망하는 로또 수량을 입력받아 수량만큼 만들어주세요.

		//lotto 번호는 1~45 (중복x) 6개번호

	//	System.out.println(makeLotto());

	//	System.out.println(makeLotto());

		//System.out.println(makeLotto());

	//	System.out.println(makeLotto());

		

		//HashSet:중복된것을 허용하지 않음

		//

		HashSet<Integer>userNum = new HashSet<>();

		userNum.add(2);

		userNum.add(12);

		//사용자가 입력한 번호를 포함시켜 lotto 번호 생성

		System.out.println(makeLotto(userNum));

		System.out.println(makeLotto(userNum));

		System.out.println(makeLotto(userNum));

		

package ch08_collection;



public class CollectionsSet {



	public static void main(String[] args) {

		

		/**

		 * Class Name    : CollectionSet

		 * Author        : KimDaeYoung

		 * Created Date : 2024. 1. 11.

		 * Version      : 1.0

		 * Purpose      : 

		 * Desciption   : 

		 */

		

		      // Set 중복을 허용하지 않음.

		      HashSet<String> stuSet = new HashSet();

		      // .add(값)

		      stuSet.add("팽수");

		      stuSet.add("팽순");

		      stuSet.add("팽수");

		      System.out.println(stuSet);

		      //.size()

		      System.out.println(stuSet.size());

		      //set은 순서 정보가 없음

		      for(String stu : stuSet) {

		         System.out.println(stu);

		      }

		      //Iterator 사용

		      Iterator(String) iterator = stuset.iterator();

		      while(iterator.hasNext()) {

		         String nm = iterator.next();

		         System.out.println(nm);

		      }

		   }



		}

package ch08_collection;

import java.util.ArrayList;
import java.util.Arrays;
import java.util.Collections;

public class CollectionList {

	public static void main(String[] args) {
	   /** 
		 *컬렉션 프레임워크는 데이터를 보다 쉽게 다룰 수 있도록 
		 * 재사용 가능한 컬렉션 클래스를 제공함.
		 * List, Set, Map
		 * 1.List:순서대로 객체를 저장하는 구조, 중복된 원소를 허용
		 *        원소에 접근하기 위해 인덱스를 사용
		 *        대표적인 ArrayList,LinkedList
 		 * 2.Set: 중복을 허용하지 않는 객체의 모음
		 *        원소의 순서는 보장하지 않음
		 *        대표: HashSet, TreeSet
		 * 3.Map: 키와 값의 쌍으로 이루어진 객체를 저장하는 구조
		 *        키는 중복될 수 없으며
		 *        각 키는 하나의 값을 가리킴.
		 *        대표 : HasMap, TreeMap      
		 * */

	     //ArrayList (동적 배열형태)
	    ArrayList<String> students = new ArrayList<>();
	 // ArrayList<String> student = new ArrayList<>(); 오른쪽은 생략가능
	    // ><  <-- 이 부분은 제네릭(Generic)이라고함.
	    //         코드에서 타입의 안정성을 보장할 수 있으면 불필요한 ㅋ캐스팅을 줄이기위해.
	    //제네릭은 객체(참조타입)만 담을 수 있음.
	    //Wrapper Class(기본타입을 객체로 만든 클래스 int, boolean....)
	    ArrayList<Integer> intList = new ArrayList<>();
	    //list 기본 메서드 . add(요소) 요소 추가시 사용가능
	    intList.add(5);
	    intList.add(10);
	    System.out.println(intList);
	    students.add("팽수");
	    students.add("동길");
	    System.out.println(students);
	    //.get(인덱스) 해당 인덱의 값을 리턴
	    System.out.println(intList.get(0));
	    System.out.println(students.get(0));
	    //. set(인덱스, 값) 해당 인덱스의 값을 변경
	    students.set(0, "팽순");
	    System.out.println(students);
	    //.contains(값) 리스트 안에 해당 값이 존재하면 true, 아닐경우 false리턴
	    System.out.println(students.contains("길동"));
	    //. indexOf(값)리스트 안에 해당 값이 어떤 인덱스에 있는지 리턴 없으면-1
	    System.out.println(students.indexOf("동길"));
	    //.insEmpty()리스트가 비어 있는지 체크 true/false
	    System.out.println(students.isEmpty());
	    //.size()리스트 요소 수
	    System.out.println(students.size());
	    //.remove(값) 해당 값이 있으면 삭제 없으면 아무일도 안일어남.
	    students.remove("홍길동");
	    //.clear() 리스트 비움 (size 0됨)
	    students.clear();
	    System.out.println(students);
	    
	    students.add("강성준");
	    students.add("권보성");
	    students.add("권유빈");
	    students.add("김기찬");
	    students.add("김대영");
	    students.add("김동우");
	    students.add("김동현");
	    students.add("김명기");
	    students.add("김영주");
	    students.add("김유정");
	    students.add("김은혜");
	    students.add("김휘건");
	    students.add("나항진");
	    students.add("문성민");
	    students.add("박진기");
	    students.add("백현진");
	    students.add("오정연");
	    students.add("유하영");
	    students.add("이예진");
	    students.add("이용빈");
	    students.add("정유진");
	   
	    for(int i =0; i<students.size(); i++) {
	    	//System.out.println(students.get(i));
	       if(students.contains("김영주")) {
	    	   System.out.println("김영주님의 출석 번호:"+(students.indexOf("김영주")+ 1));
	           break;
	       }
	    }
	    //1. 리스트 복사(얕은 복사)
	    ArrayList<String> stu = students;
	    System.out.println(stu);
	    stu.set(0, "성준");
	    System.out.println(stu);
	    System.out.println(students);
	    //2. 깊은 복사
	    ArrayList<String> stu2 = new ArrayList<String>(stu);
	    ArrayList<String> stu3 = new ArrayList<>();
	    stu3.addAll(stu);
	    stu2.add("nick");
	    stu3.add("judy");
	    System.out.println(stu);
	    System.out.println(stu2);
	    System.out.println(stu3);
	    //향상된 for문 (값만 필요할때)
	    for(String str: students) {
	    	System.out.println(str);
	    }
	    //일반 배열도 가능
	    String [] strArr = {"1","2","3"};
	    for(String str: strArr) {
	    	System.out.println(str);
	    }
	    // 값을 주면서 선언
	    ArrayList<Integer> numbers = new ArrayList<>(Arrays.asList(10,20,1,2));
	    //컬렉션 sort
	    System.out.println(numbers);
	    //정렬 오른차순
	    Collections.sort(numbers);
	    System.out.println(numbers);
	    //정렬 내림차순
	    Collections.sort(numbers, Collections.reverseOrder());
    	System.out.println(numbers);
	
	
	}

}
