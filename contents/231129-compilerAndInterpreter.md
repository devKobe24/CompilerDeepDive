# 컴파일러와 인터프리터. 🤿

번역기 중에서 **컴파일러**와 **인터프리터**는 **고급언어**로 작성된 프로그램을 **입력자료**로 하여 **번역**하는 가장 **대표**적인 번역기들입니다.

**컴파일러**는 **고급 프로그래밍 언어**를 **기계어**로 **번역**하는 프로그램으로, 그 **과정**은 일반적으로 **6단계**로 구분됩니다.

1. 어휘분석 단계.
2. 구문분석 단계.
3. 의미분석 단계.
4. 중간 코드 생성 단계.
5. 코드최적화 단계.
6. 목적코드 생성 단계.

**원시 프로그램**은 이러한 **단계**를 **거쳐** **기계코드로 번역**이 되는데, 이러한 단계를 **구성**하는 **소프트웨어**가 **컴파일러**입니다.

**인터프리터**는 컴파일러와 같은 단계를 거치지 않고, **원시 프로그램**을 **그때그때 처리**하므로 **인터프리터의 처리과정**은 컴파일러와는 **다릅니다.**

실제 입력 프로그램을 처리하는 과정을 살펴보면, **컴파일러**는 입력 프로그램의 **전체 문장**을 **입력된 순서대로 처리**하여, **전체적**인 **하나**의 **목적 프로그램을 완성**하고, 이것은 **후에 로드(load)** 되어 **실행**하게 됩니다.

반면에 **인터프리터**는 입력 프로그램의 **논리적인 순서**에 따라 **문장 단위로 번역**한 후, **곧바로 실행**하기 때문에 사용자는 실행결과를 그때그때 보고 다른 명령을 또다시 실행하는 이른바 컴퓨터와의 대화가 가능해집니다.

또한 **인터프리터 기법**은 사용자가 외부에서 볼 때, 입력된 고급언어의 매 문장단위를 실행하기 때문에 마치 고급언어가 컴퓨터에서 곧바로 실행되는 기계어처럼 보입니다.

따라서 **인터프리터 기법**을 **시뮬레이션(simulation) 기법**이라고도 합니다.

반면에 **컴파일러** 등과 같이 번역만 하는 것을 **번역기법**이라고 합니다.

앞에서 언급한 순수한 컴파일러 기법이나 순수한 인터프리터 기법은 너무 극단적인 방법이므로 잘 사용하지 않으며, **일반적으로 이 두 기법을 함께 사용하여 컴퓨터에 구현**합니다.

다시 말하면 **프로그램을 좀 더 실행시키기 쉬운 형태로 번역**한 후, 그 번역된 형태의 프로그램을 **디코드(decode)해서 시뮬레이션 기법으로 실행**합니다.

# 1️⃣ 컴파일러 기법과 인터프리터 기법의 특성.

실제로 프로그램의 실행과정에서 일부 프로그램 구조는 번역이 되면 매우 간결하고 효율적이지만, 어떤 프로그램 구조는 원래의 형태를 유지하였다가 **실행되는 동안에 처리하는 것이 보다 더 효율적**입니다.

반복문이나 계속 호출되는 부프로그램처럼 많은 횟수로 반복 처리되는 프로그램인 경우에는 **컴파일러 기법이 큰 장점**을 갖습니다.

이 경우 **인터프리터 기법** 같으면, 매번 반복 처리될 때마다 **또다시 디코딩**해야 하지만, **컴파일러 기법**은 **전체적으로 디코딩**하게 되면, 그다음부터는 **실행만 하므로** 전체 실행시간 면에서 **효율적**입니다.

**그러나** **몇 줄**의 **원시 프로그램**이 때로는 **몇백 개**의 **기계어**로 **번역**되기 때문에 **컴파일러 기법은 커다란 기억장소가 필요**해집니다.

특히 **입출력 명력**은 **입출력 포맷(format)** 을 위한 코드 외에 **기계상태 파악코드와 버퍼 등**으로 인하여 **기억장치가 더 커야 합니다.**

아래 그림은 컴파일러 기법의 처리과정을 보여주는 것 입니다.

<img src = "https://github.com/devKobe24/images/blob/main/CPDD-7.png?raw=true"></br>

**인터프리터 언어**는 **컴파일러 기법**의 특징과 성격이 거의 **반대**입니다.

고급언어로 작성된 원시 프로그램은, 동일한 수행을 나타내는 중간코드로 번역되므로 **큰 기억장소를 요구하지는 않지만**, **실행하는 동안에 디코딩하는 시간이 많이 필요**하고, 또한 **반복문 등의 경우는 반복해서 디코딩**되므로 **실행시간이 길어**집니다.

그러나 사용자가 실행과정을 눈으로 볼 수 있고, 일문일답식의 대화가 가능하며, 언어에 사용되는 자료를 **동적으로 정의**하는 등의 융통성이 있습니다.

**인터프리터 기법의 처리과정**을 살펴보면, **고급언어로 작성**된 **원시 프로그램**을 **중간코드**로 **변환**하고, **변환**된 **중간코드를 명령어 단위로 가져다가 디코드하고 실행**합니다.
그리고 **명령어의 주소를 하나 늘린 후, 다음 명령어를 가져옵니다.**
따라서 **반복문 등이 있을 때는 반복횟수만큼이나 명령어를 계속 가져와서 디코드하고 실행**하므로, 단 한 번의 번역으로 끝마치는 컴파일러 기법에 비해 **시간이 많이 소요됨**을 알 수 있습니다.

인터프리터의 디코딩 및 실행과정을 표현하면 아래 그림과 같습니다.

<img src = "https://github.com/devKobe24/images/blob/main/CPDD-8.png?raw=true"></br>

# 2️⃣ 컴파일러 언어와 인터프리터 언어.

**컴파일러 언어**에는 FORTRAN, ALGOL, PL/I, PASCAL, COBOL, C, JAVA 등이 있습니다.

이 언어들은 프로그램 대부분이 실제 기계의 기계어로 번역되고, 입출력 등의 기계언어와 유리된 일부 원시연산만 실행 시간 보조루틴(run-time support routine) 등을 사용하여 시뮬레이션으로 처리합니다.

**인터프리터 언어**에는 BASIC, LISP, SNOBOL, APL 언어 등으로 이들 언어는 적당한 중간언어(intermediate language)로 번역되고, 중간언어는 인터프리터에 의하여 실행됩니다.

컴파일러 언어라고 해서 **반드시 컴파일러에 의하여 번역된 후 실행되는 것은 아닙니다.**

**컴파일러 언어**도 **인터프리터에 의하여 수행될 수 있습니다.**
또한 **인터프리터 언어**도 **컴파일러에 의하여 수행될 수 있습니다.**

그러나 **언어의 특성상** **컴파일러 언어는 컴파일러 기법**을, **인터프리터 언어는 인터프리터 언어**를 **사용하는 것이 효율적**입니다.
