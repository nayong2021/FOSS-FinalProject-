# Code Chunk

**추후에 변경될 수 있음.**

**Markdown Preview Enhanced** 는 코드의  출력을 문서에 렌더링 할 수 있다.


    ```bash {cmd}
    ls .
    ```

    ```bash {cmd=true}
    ls .
    ```

    ```javascript {cmd="node"}
    const date = Date.now()
    console.log(date.toString())
    ```

> ⚠️ **스크립트 실행은 기본적으로 비활성화되어 있으며 Atom 패키지 또는 VSCode 확장의 환경설정에서 명시적으로 활성화해야 한다.**
>
> 이 기능은 보안상 취약하므로 주의하여 사용하기 바란다!
> 스크립트 실행이 활성화된 상태에서 누군가 악성 코드로 마크다운을 열면 컴퓨터가 해킹될 수 있다.
>
> 이곳에서 설정: `enableScriptExecution`

## 명령 & 키보드 단축키

- `Markdown Preview Enhanced: Run Code Chunk` 또는 <kbd>shift-enter</kbd>
  커서가 있는 곳의 code chunk 하나를 실행한다.
- `Markdown Preview Enhanced: Run All Code Chunks` 또는 <kbd>ctrl-shift-enter</kbd>
  모든 code chunk를 실행한다.

## 서식

code chunk 옵션은 <code>\`\`\`lang {cmd=your_cmd opt1=value1 opt2=value2 ...}</code>형식으로 설정할 수 있다.
만약 속성의 값이 true 의 경우는, 생략할 수 있다. (예: {cmd hide} 는 {cmd=true hide=true} 와 동일).

**lang**
코드 블록이 강조 표시해야 하는 문법으로 가장 앞에 놓여야 한다.

## 기본 옵션

**cmd**
실행할 명령.
`cmd` 가 지정되지 않은 경우 then `lang` 를 명령으로 사용한다.

예시:

    ```python {cmd="/usr/local/bin/python3"}
    print("This will run python3 program")
    ```

**출력**
`html`, `markdown`, `text`, `png`, `none`

어느 형식으로 코드의 출력을 렌더링 할 지 정의한다.

`html` 은 html로 출력을 추가한다.
`markdown` 은 출력을 markdown으로 분석한다. (MathJax 및 graphs는 지원되지 않지만 KaTex는 지원한다.)
`text`는 출력을 `pre` 블록에 추가한다다.
`png` 는 출력을 `base64` 이미지로 추가한다.
`none` 은 출력을 표시하지 않는다.

예시:

    ```gnuplot {cmd=true output="html"}
    set terminal svg
    set title "Simple Plots" font ",20"
    set key left box
    set samples 50
    set style data points

    plot [-10:10] sin(x),atan(x),cos(atan(x))
    ```

![screen shot 2017-07-28 at 7 14 24 am](https://user-images.githubusercontent.com/1908863/28716734-66142a5e-7364-11e7-83dc-a66df61971dc.png)

**args**
명령에 추가되는 인자. 예시:

    ```python {cmd=true args=["-v"]}
    print("Verbose will be printed first")
    ```

    ```erd {cmd=true args=["-i", "$input_file", "-f", "svg"] output="html"}
      # output svg format and append as html result.
    ```

**stdin**
`stdin` 이 true로 설정된 경우 코드는 파일이 아닌 표준 입력으로 전달된다.

**hide**
`hide`는 code chunk는 숨기지만 출력 결과는 표시한다. 기본값: `false` 
예시:

    ```python {hide=true}
    print('you can see this output message, but not this code')
    ```

**continue**
`continue = true`로 설정된 경우, code chunk는 이전 code chunk에 이어 연속적으로 실행된다.
continue = id로 설정된 경우, code chunk는 동일한 id가 설정된 code chunk에 이어 연속적으로 실행된다. 
예시:

    ```python {cmd=true id="izdlk700"}
    x = 1
    ```

    ```python {cmd=true id="izdlkdim"}
    x = 2
    ```

    ```python {cmd=true continue="izdlk700" id="izdlkhso"}
    print(x) # will print 1
    ```

**class**
`class="class1 class2"`로 설정하면 `class1 class2`가 code chunk 에 추가된다.

- `line-numbers` 클래스가 추가된 code chunk에는 행 번호가 표시된다.

**element**
뒤에 추가하고자 하는 요소.
아래의 **Plotly** 예제를 참조하기 바람.

**run_on_save** `boolean`
markdown file이 저장될 때 code chunk를 실행한다. 기본값 `false`.

**modify_source** `boolean`
markdown 소스 파일에 code chunk의 출력 결과를 직접 삽입한다. Default `false`.

**id**
code chunk의 `id`. `continue` 옵션을 사용할 때 유용하다.

## Macro

- **input_file**
  `input_file` 은 markdown 파일과 동일한 디렉토리에 자동으로 생성되며 `input_file`에 복사 된 코드 실행이 완료되면 자동으로 삭제된다. 
  기본적으로 프로그램 인수의 맨 끝에 추가된다.
  그러나, `$input_file` 매크로의 `args` 에 `input_file` 이 저장될 위치를 설정할 수도 있다. 예:

      ```program {cmd=true args=["-i", "$input_file", "-o", "./output.png"]}
      ...your code here
      ```

## Matplotlib
`matplotlib = true`로 설정되면 python code chunk가 preview에 즉시 그래프를 그릴 것이다.
예:

    ```python {cmd=true matplotlib=true}
    import matplotlib.pyplot as plt
    plt.plot([1,2,3, 4])
    plt.show() # show figure
    ```

![screen shot 2017-07-28 at 7 12 50 am](https://user-images.githubusercontent.com/1908863/28716704-4009d43a-7364-11e7-9e46-889f961e5afd.png)

## LaTeX

Markdown Preview Enhanced는 `LaTeX` 컴파일도 지원한다. 이 기능을 사용하려면 [pdf2svg](extra.md?id=install-svg2pdf) 와 [LaTeX engine](extra.md?id=install-latex-distribution)을 설치해야 한다. 그 다음 LaTex code chunk를 다음과 같이 작성할 수 있다:

    ```latex {cmd=true}
    \documentclass{standalone}
    \begin{document}
      Hello world!
    \end{document}
    ```

![screen shot 2017-07-28 at 7 15 16 am](https://user-images.githubusercontent.com/1908863/28716762-8686d980-7364-11e7-9669-71138cb2e6e7.png)

### LaTeX 출력 설정

**latex_zoom**
`latex_zoom=num`이 설정되면, 출력 결과는 `num` 배로 표시된다.

**latex_width**
출력 결과의 너비.

**latex_height**
출력 결과의 높이.

**latex_engine**
`tex` 파일을 컴파일하는 데 사용되는 latex engine을 설정한다. 기본값으로 `pdflatex` 를 사용한다.

### TikZ example

`tikz` 그래프를 그리는 경우 `standalone` 을 사용하는 것을 추천한다.
![screen shot 2017-07-14 at 11 27 56 am](https://user-images.githubusercontent.com/1908863/28221069-8113a5b0-6887-11e7-82fa-23dd68f2be82.png)

## Plotly

Markdown Preview Enhanced를 이용하면 [Plotly](https://plot.ly/) 를 쉽게 그릴 수 있다.
예를 들어:
![screen shot 2017-10-20 at 10 41 25 am](https://user-images.githubusercontent.com/1908863/31829580-526a0c06-b583-11e7-82f2-09ea7a0b9672.png)

- 첫 번째 줄의 `@import "https://cdn.plot.ly/plotly-latest.min.js"`는 [file import](file-imports.md) 기능을 사용하여 `plotly-latest.min.js` 파일을 import한다. 
  그러나 성능 측면에선 로컬 디스크로 js 파일을 다운로드하는 것이 더 좋다.
- 그 다음, 나머지는 `javascript` code chunk를 쓰는 것이다.

## Demo

entity-relation diagram을 [erd](https://github.com/BurntSushi/erd) 라이브러리로 그리는 방법의 데모이다.

    ```erd {cmd=true output="html" args=["-i", "$input_file" "-f", "svg"]}

    [Person]
    *name
    height
    weight
    +birth_location_id

    [Location]
    *id
    city
    state
    country

    Person *--1 Location
    ```

`erd {cmd=true output="html" args=["-i", "$input_file", "-f", "svg"]}`

- `erd` 사용중인 프로그램 (_처음에 프로그램을 설치해야 함_)
- `output="html"` `html` 로 출력 결과를 추가한다.
- `args` 필드는 사용할 인자를 지정한다.

미리보기에서 `run` 버튼을 클릭하여 코드를 실행할 수 있다.

![erd](https://user-images.githubusercontent.com/1908863/28221395-bcd0bd76-6888-11e7-8c6e-925e228d02cc.gif)

## Showcases (지난 정보)

**bash**
![Screen Shot 2016-09-24 at 1.41.06 AM](https://i.imgur.com/v5Y7juh.png)

**gnuplot with svg output**
![Screen Shot 2016-09-24 at 1.44.14 AM](https://i.imgur.com/S93g7Tk.png)

## 한계

- 아직 `ebook` 출력에서 작동하지 않는다.
- `pandoc document export`를 사용할 때 버그가 있을 수 있다.

[➔ 프레젠테이션](presentation.md)
