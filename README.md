#vimconfig

vim 플러그인을 쉽게 설치하기 위한 프로젝트.

사용된 자원

- Bundle
- Bash script


#설치하기
    git clone https://github.com/ygpark/vimconfig.git ~/vimconfig
    ~/vimconfig/install.sh

--> Above is Orignal Code


    git clone https://github.com/ipbanks/vimconfig.git ~/vimconfig
    ~/vimconfig/install.sh

#Error 처리

Q) 아래와 같은 Error가 Vim을 실행할때 나오면.. 
Error detected while processing /home/me_and/.vim/plugin/cscope_maps.vim:
line   42:
E568: duplicate cscope database not added
A) The fix was then to edit the ~/.vim/plugin/cscope_maps.vim file 
    to add set nocscopeverbose immediately before the cs add ...
 https://stackoverflow.com/questions/41601225/how-to-fix-duplicate-cscope-is-it-a-better-way
 
 실제 vimconfig구조에선.. 
 ~/.vim/bundle/cscope_macros.vim/plugin/cscope_macros.vim 에서 아래와 같이 고쳤는데.. 
 set nocscopeverbose 와 set cscopeverbose 가 두번불리네? 그래도 에러메세지 없으니.. -_-;; 
 
 40     " add any cscope database in current directory
 41     if filereadable("cscope.out")
 42         set nocscopeverbose
 43         cs add cscope.out
 44     " else add the database pointed to by environment variable
 45     elseif $CSCOPE_DB != ""
 46         cs add $CSCOPE_DB
 47     endif
 48
 49     " show msg when any other cscope db added
 50     set cscopeverbose
 

#디렉토리 구조


|    이름    |            내용                                                 |
| ---------- | --------------------------------------------------------------- |
| /snippets  | SnipMate 플러그용 snippets (자동 설치 미지원)                   |
| /plugins   | 커스텀 플러그인 <br/> vimrc에서 'source' 명령으로 이 디렉토리의 파일들을 incldue한다.  |
| README.md  | 지금 읽고 있는 파일                                             |
| install.sh | 설치파일 <br/>  ~/.vimrc 파일과 ~/.vim/ 를 생성한다.            |
| vimrc      | ~/.vimrc -> ~/vimconfig/vimrc                                   |



# 유용한 vim 명령어
	[ + I				같은 파일에서 심볼 위치 검색
	:set fileencoding=utf-8		파일 인코딩 변경
	v]}zf				코드의 { 부분에서 영역 접기
	zo				영역 펼치기
