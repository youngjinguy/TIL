# Test Double
소프트웨어 테스트에서 사용되는 가짜 객체를 뜻한다. Test Double 대표적인 종류는 Dummy, Fake, Stub, Spy, Mock 5가지가 있다.

## Dummy
Dummy는 사전적 의미대로 가짜 객체이다. 즉 테스트를 수행하기 위해서는 필요하지만, 실제 기능상에 영향이 주지 않는 경우 객체인 경우에 Dummy 객체로 대신할 수 있다.

아래와 같은 MemberService가 있고, 이것을 테스트 하려고 한다고 가정해보자.
``` kotlin
interface Logger {
    fun info(message: String)
}

class MemberService(
    private val logger: Logger
) {
    fun getMember(memberId: String) {
        logger.info(memberId)
        // logic
    }
}
```

구현되어 있는 코드를 테스트 한다고 했을 때, 실제 `Logger`는 로직과 관련이 없지만 테스트를 위해 필요한 객체이다. 이런 케이스에서 Dummy 객체를 사용할 수 있다.

``` kotlin
class DummyLogger : Logger {
    override fun info(message: String) {
        // nothing
    }
}

class MemberServiceTest() {
    fun test() {
        // Dummy
        val dummyLogger = DummyLogger()
        val memberService = MemberService(dummyLogger)
        memberService.getMember("memberId")
    }
}
```
## Fake
## Stub
## Spy
## Mock
