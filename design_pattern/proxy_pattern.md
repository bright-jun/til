# 프록시 패턴(Proxy Pattern)

- 프록시(Proxy) : 대리자, 대변인
  - 프록시(대리자, 대변인)에게 어떤 일을 대신 시키는 것

![](https://upload.wikimedia.org/wikipedia/commons/thumb/7/75/Proxy_pattern_diagram.svg/2560px-Proxy_pattern_diagram.svg.png)

```java
import java.util.*;

interface Image {
    public void displayImage();
}

//on System A
class RealImage implements Image {
    private String filename;
    public RealImage(String filename) {
        this.filename = filename;
        loadImageFromDisk();
    }

    private void loadImageFromDisk() {
        System.out.println("Loading   " + filename);
    }

    @Override
    public void displayImage() {
        System.out.println("Displaying " + filename);
    }
}

//on System B
class ProxyImage implements Image {
    private String filename;
    private Image image;

    public ProxyImage(String filename) {
        this.filename = filename;
    }

    @Override
    public void displayImage() {
        if (image == null)
           image = new RealImage(filename);

        image.displayImage();
    }
}

class ProxyExample {
    public static void main(String[] args) {
        Image image1 = new ProxyImage("HiRes_10MB_Photo1");
        Image image2 = new ProxyImage("HiRes_10MB_Photo2");

        image1.displayImage(); // loading necessary
        image2.displayImage(); // loading necessary
    }
}

class RealExample {
  public static void main(String[] args) {
    Image image1 = new RealImage("HiRes_10MB_Photo1");
    Image image2 = new RealImage("HiRes_10MB_Photo2");

    image1.displayImage(); // loading necessary
    image2.displayImage(); // loading necessary
  }
}
```

- why?
  - 예를 들어 용량이 큰 이미지와 글이 같이 있는 문서를 화면에 띄운다고 가정
    - 텍스트는 용량이 작아서 빠르게 로딩
    - 이미지는 용량이 커서 느리게 로딩
    - 둘 다 로딩이 다 끝난 후에 화면에 출력된다면
      - 느리게 로딩
    - 각각 로딩이 될 때마다 화면에 출력된다면
      - 각각 빠르게, 느리게 로딩
  - 각각 로딩이 될 때마다 출력하는 방식이 사용자 친화적
    - 이와 같은 방식을 가지려면 텍스트 처리용 프로세스, 이미지 처리용 프로세스를 별도로 운영
  - `ProxyExample`클래스에서 `RealImage`클래스에 직접 접근하지 않고 `ProxyImage`클래스에서 객체를 생성하여 대신 일을 수행하는걸 확인할 수 있다.
    - ```
      ProxyExample
      
      Loading    HiRes_10MB_Photo1
      Displaying HiRes_10MB_Photo1
      Loading    HiRes_10MB_Photo2
      Displaying HiRes_10MB_Photo2
      ```
  - `RealExample`클래스에서 `RealImage`클래스에 직접 접근하여 객체를 생성하여 대신 일을 수행하는것
    - ```
      RealExample

      Loading   HiRes_10MB_Photo1
      Loading   HiRes_10MB_Photo2
      Displaying HiRes_10MB_Photo1
      Displaying HiRes_10MB_Photo2
      ```

- 장점
  - 사이즈가 큰 객체가 로딩되기 전에도 프록시를 통해 참조를 할 수 있다.
  - 실제 객체의 public, protected 메소드를 숨기고 인터페이스를 통해 노출시킬 수 있다.
  - 로컬에 있지 않고 떨어져있는 객체를 사용할 수 있다.
  - 원래 객체에 접근에 대해 사전처리를 할 수 있다.
- 단점
  - 객체를 생성할 때 한 단계를 거치게 되므로, 빈번한 객체 생성이 필요한 경우 성능이 저하될 수 있다.
  - 프록시 내부에서 객체 생성을 위해 스레드가 생성, 동기화가 구현되어야 하는 경우 성능이 저하될 수 있다.
  - 로직이 난해해져 가독성이 떨어질 수 있다. 

## 참고

- [https://velog.io/@newtownboy/%EB%94%94%EC%9E%90%EC%9D%B8%ED%8C%A8%ED%84%B4-%ED%94%84%EB%A1%9D%EC%8B%9C%ED%8C%A8%ED%84%B4Proxy-Pattern](https://velog.io/@newtownboy/%EB%94%94%EC%9E%90%EC%9D%B8%ED%8C%A8%ED%84%B4-%ED%94%84%EB%A1%9D%EC%8B%9C%ED%8C%A8%ED%84%B4Proxy-Pattern)
- [https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9D%EC%8B%9C_%ED%8C%A8%ED%84%B4](https://ko.wikipedia.org/wiki/%ED%94%84%EB%A1%9D%EC%8B%9C_%ED%8C%A8%ED%84%B4)