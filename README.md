# my-idea-live-templates

Some nice templates (mostly unit test / java) I use on a daily basis to spare some time.
All of them will provide the right cursor-step, when needed, to guide you. 


### To use : import it through File / Manage IDE Settings / import, and select settings.zip file.

### tu
will generate a simple junit 5 test template, with assertAll

```java
    @Test
    public void should_when() {
        // Arrange
        String actual = "";
        // Mock
        
        // Act
        
        // Assert
        Assertions.assertAll(
                () -> assertThat(actual).isEmpty(),
                () -> assertThat(actual).isEqualTo("")
        );    
        
    }
```


### ptest
will generate a parametrized unit test (junit 5 ), with a method source and stream of arguments

```java
    @ParameterizedTest
    @MethodSource(value = "iWillTypeHereMyMethodSourceNameItsMagic")
    public void shouldTypeHereWhatIExpect_whenImRunningSomeActionInActSection(String firstString, String secondString, String thirdString) {
        // Arrange
        String actual = "";
        // Mock

        // Act

        // Assert
        Assertions.assertAll(
            () -> assertThat(firstString).isEmpty(),
            () -> assertThat(secondString).isEqualTo(""),
            () -> assertThat(thirdString).isNotNull()
        );

        }

    private static Stream<Arguments> iWillTypeHereMyMethodSourceNameItsMagic() {
    
        return Stream.of(
            Arguments.of("string1", "string2", "string3"),
            Arguments.of("string4", "string5", "string6"),
            Arguments.of("string7", "string8", "string9")
        );
    }

```




### asall
will generate an assertAll (with assertj)

```java
        Assertions.assertAll(
            () -> assertThat(actual).isEmpty(),
            () -> assertThat(actual).isEqualTo("")
        );

```

### setup
will generate a setup @BeforeEach Method

```java
    @BeforeEach
    public void setup() {
        // init classes to test here.
    }


```


### venever
will generate a mockito verify never()

```java
    Mockito.verify(myMock,Mockito.never()).aMethodThatIsNotSupposedToHappen();

```

### vetimes
will generate a mockito verify with the expected mock with number of hits.

```java
Mockito.verify(myMock,Mockito.times(3)).doingThisAwesomeStuff(/* maybe your params here */) ; 
```


### verifonce
will generate a mockito verify with the expected mock one time
```java
  Mockito.verify(myMock).doingThis();
```