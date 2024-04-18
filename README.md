--------------------------Git konfigurasiya github ssh key-------------------------------------------------------------------------------------

bash =>  - ssh-keygen -t rsa -b 4096 -C "github" && cat ~/.ssh/id_rsa.pub
| ssh-keygen -t rsa -b 4096 -C "github" && cat ~/.ssh/id_rsa.pub => 1) git -keygen -o => enter , enter , enter 2) cat ~/.ssh/id_rsa.pub (copy) |

burda ssh key gelir -> 'xyz' - bunu aliriq yeni xyz di sonrada aparib 
git profile => settings => ssh and gps keys => new ssh key buttonuna click edib 
yenisini elave edecem - title = 'ozun ad ver' key='xyz' olusdurduqumuz ssh key

ssh => iki key yaradir privite and public - pub(public) olani gitlab, githuba 
elave edirik biz gitlaba sorqu atanda biz olduqunu tanisin die
Bu onun ichindirki biz her defe git pull edende bizden user name ve password isdemesin



----------------------------------------------------------------------------------------------------------------------------------------------


*! ashaqidaki shekilde sehf gedib =>  Mərkəzləşdirilmiş Versiya Nəzarət Sistemi

![alt text](image-5.png)


![alt text](image-6.png)


*Git => bizim versialar arasindaki keçid işlərini və etdiyimiz dəyişiklikləri uzaq bir servere əlavə etməyimizə köməklik edən bir alətdir(tooldu)


* GitHub => Bizim localdaki fayillari saxlayan Uzaqdaki server demek olar

![alt text](image-7.png)

![alt text](image-8.png)

![alt text](image-9.png)

![alt text](image-10.png)

* git init - .git uzantili Projevtle eyni path de folder yaradir (Local Repository)

* git config --global init.defaultBranch <branchName> => default branch-in adini dəyişmək => git config --global init.defaultBranch develop

* ![alt text](image.png)

* 3 areas var => 1 Working directory(iş direktoriyasi) ".git uzantisi olan folderdi"- Biz gore Bilirik  bu areani , 2 Staging Area .git folderinin daxilinde olur, 
  3 Repository .git Folderinde olur bu bizim local repositoridi
* git init etdikde her fayil elave olunur Working directory-e , git add etdikde Staging Area , git commit etdikde Local Repository e

* ![alt text](image-1.png)

* ![alt text](image-4.png)

* ![alt text](image-3.png)

* git add - Dəyişikləri Stage alanina əlavə edir

* git commit -m "Commit 1" - Dəyişikləri Local Repository -ə əlavə edir Stage dən çıxardıb .git -ə yazir 

* git status - Dəyiklikləri izləyir Aktiv olan Branch üzərindəki dəyiklikləri görsədir

* git reset HEAD <File Name> - Local Repositorideki dəyişiklikləri Stage Alanına daşıyır

* git reset HEAD fayilName.uzantisi => eger edilen deyisiklik add olub stage area düşibsə həmin dəyişiyliyi change alir yeni working area alir
  eger sonrada git checkout -- fileName.uzantisini yazarsaq bütün dəyişiklik geri alinacaq 


------------------------------------------RESET------------------------------------------------------------------------------------------------------

* git reset --soft HEAD^ => son commiti geri alir Staged Area ya |local Repository -> Staged Area| => git reset --soft HEAD^ 
* git reset --mixed HEAD^ => son commiti geri alir Working Area ya |local Repository -> Working Area| => git reset --mixed HEAD^ 
* git reset --hard HEAD^ => son commiti geri alir Working Areadan bile silir -> |butun deyisiklikler silinir|=> git reset --hard HEAD^ 


-----------------------------------------------------------------------------------------------------------------------------------------------------

* git resotere <File Name>  --stage - Local Repositorideki dəyişiklikləri Stage Alanına daşıyır 

* git branch <Branch Name> - Yeni bir branch yaradir

* git branch -a - Remote Repositorideki Branchlerin hamisini görsədir

* git checkout - Her hansisa Branch-ə getməmizi sağlayır

* git checkout -b <Branch Name> - yeni branch yaradib hemin branche getməmizi sağlayır

* git merge - isdediyimiz branchi hazirda olduqumuz branch ile birləşdirir
	      Eyni dosyada eyni setirde dəyişliklər olubsa hansini seçmek lazimdi diə önərilər edər
  git merge => localdaki branchleride bir birine birleshdirir meselen men x branchinde ishleyirem ve birde menim y branchim var men bu iki branchi birlesdirib tek commit altinda push etmek isdeyirem bu zaman x branchine gelib y branchini merge edib sonra tek commitle pushlayiram ve x branchini silirem

* Bizim bugFix adinda branchimiz var ve biz burda bug fix eddikden sonra Uzaq Repodaki masteri bura pull edib sonra push etmeliyik bu işi iki cür görmək olar birinci       
  olduqumuz bugFix brançində "git pull origin master"  edirikgit yada qayidiriq master branchine orda "git pull" edirik sonra bugfix brancimize gelib orda "git merge develop" edirik (
    1) git checkout -b bugFix (birdene test.txt fayli yaradaq)
    2) git pull origin master (herzaman et confilict olmasin sonra)
    3) git add.  ve git commit -m"upd"
    4) git pull origin master      bundan      sonra git push
    4 ci ni belede etmek olar => git checkout master   sonra git pull   sonra   git checkout bugfix   sonra git merge master   sonra git push

* git remote - Localdaki repositorimizi uzaqdaki repomuza baqlamaqimizi sağlayır
               yəni gitHub, gitLab kimi uzaq Repolara(Bir gitHub repozitorisi yaradiriq
               create new repositori və orda zatən Local Repomuzu Uzaqdaki gitHup Repo 
               ilə necə əlaqələndirmək lazimdi qeyd edilir) Deyisiklikleri elave etmir Local ile Remot daki Repolari baqlayir

* git clone - Uzaq serverdeki bir proyekti Kəndi komputerimizə indirməmizi sağlayır

* git pull - Uzaq serverdeki master branchindeki en son dəyiklikləri olduğumuz branchə indirməmizi sağlayır

* git push - Local Branchimizdəki dəyiklikləri Uzaq Serverdeki Repozitorimizə göndərir

*! WORKING DIRECTORY - "git add . (yaxud git add fileName)" dəyiklikləri Localdaki STAGE AREA əlavə edir 
 "git commit" dəyişiklikləri LOCAL REPOYA yəni .git -ə əlavə edir 
 "git push" LOCAL REPO daki yəni .git dəki dəyiklikləri REMOTE REPO-ya göndərir
 "git pull / git fetch" REMOTE REPO-dan LOCAL REPO-ya çəkir 
 "git merge" ederek LOCAL REPO-dan LOCAL WORKING DIRECTORY-ya Çəkir
 "git fetch + git merge = git pull"
 
*FORK - Hər hansisa Remote Reponu fork edirik sonra bu repo bizim Remote serverimize(gitHub Hesabimiza elave edilir) ondan sonra Komputerimizde
        git clone forklediyimizRepo(öz gitHubimizdaki url) sonra Dəyişkliklər etdim push etdim öz Remote Repoma sonrada ordan PR(pull request)
        yaradiriq sonrada Projectini forklediyimiz istifadeci merge edir

* GitHub Nədir ? - Projelərimizi Private və Public olaraq əlavə edə biləcəyimiz DEPOLAMA alanidir

* əgər bir faylda dəyişiklik edib git add ve commit etdikdə sonradan faylda dəyişiklik etdikdə birdə git add yazmaqa ehtuyac yoxdur 
  git commit yazmaq kiffayet edir(git commit -a -m "commit")

* git remote - "origin" 'gelecek origin git@github.com:gitUserName/RepositoryName.git' bu addressi saxlayir (Remote daki Reponun addressi)

* pull request => PR yaratmaq - yeni branch yaradib push etdikde hersey okeyse hemin branchi MR (MERGE REQUEST) edirik main branchimize sonrada yaratdiqimiz branchi silirik
  localdan silmek ichin ise terminalda   "git branch -d LocalBranchName"   Remote branchini silmekden ötri isə  "git push origin --delete remoteBranchnName"
  1 "git push origin --delete remoteBranchnName"  | "git push origin -dremoteBranchnName"
  2  "git branch -d LocalBranchName"

* git branch m <old branch name> <new branch name> - branchin adini deyismek

* git log => hazirda olduqumuz branchdeki commitleri görə bilərik olurda hansisa fayil silinse yada nese deyisiklik silsek  
  biz git log ederek evelki commiti checkout ede bilerik "git checkout commit1 -- . " yada sol terefde fayili "discard changes" edirik 

* git diff => fayillarda edilen deyisikleri görsədir 

* git checkout -- fileName.uzantisi => eger fayilda sehfen edilen deyisiklikleri geri almaq isdeyirikse eger birden chox fayilsa adlarini qeyd etmekdense -- . qoya bilerik

* git rm fileName.uzantisi => hemin fayli silir(fayil silmek) => fayl local Repoda(add commit) olsa da silir 
  use --cached to keep the file, or -f to force removal => git rm --cached fileName.uzanti  | git rm -f fileName.uzanti 

* git rm -r folderName/ => folder ve daxilindeki filelari silir  => folder local Repoda(add commit) olsa bile 

* git mv text.txt test.txt => text.txt faylin adi deyishib test.txt olur

* git mv text.txt folderName/ => foldere dashiyir ex: git mv text.txt dosya/ => dosya/text.txt  2) git mv text.txt dosya/abc.txt => dosya/abc.txt

* alias özəlliyi => git config --global alias.st status => git status yerine git st yazacayiq (git status da ishe yarayir)

* git log -p -2 => son iki commiti gorsedecek (-p = --patch)

* git log --pretty=oneline => 
                           ca82a6dff817ec66f44342007202690a93763949 Change version number
                           085bb3bcb608e1e8451d4b2432f8ecbe6306e7e7 Remove unnecessary test
                           a11bef06a3f659402fe7563abf99ad00de2209e6 Initial commit

* git log --since=2.weeks => son iki hefdede olunan commintleri gorsedecek