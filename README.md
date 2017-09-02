# AndroidOpenCV
android OpenCV

Android에 OpenCV를 연동하는 방법
1. https://github.com/opencv/opencv/releases 최신 android-sdk를 받는다.
2. android에서 c++ 연동 프로젝트 생성한다.
3. File -> New -> Import Module 에서 OpenCV-android-sdk/sdk/java 폴더를 경로로 지정하여 추가
4. 프로젝트의 Default Module 에서 openCVLibrary330 모듈을 추가해야 한다. File -> Project Structure 에서 Modules 항목에 있는 app을 선택하고 Dependencies 탭에서 + 버튼을 눌러 Module Dependency를 추가한다.
5. 다운로드 받았던 OpenCV-android-sdk 폴더에 /sdk/native 에 위치한 lib 폴더를 현 프로젝트 main의 하위 폴더로 복사하는데 폴더 이름을 JniLibs 로 변경하여 복사한다.
6. CMakeLists.txt 파일에서 일부 라인의 경로를 수정한다.



CMakeList.txt

해당파일에서 경로설정을 따로 해줘야함

경로 설정해야 하는 라인

OpenCV-android-sdk 폴더의 경로를 설정

set(pathOPENCV /Users/nextus/Downloads/OpenCV-android-sdk)

현재 안드로이드 프로젝트의 경로를 설정

set(pathPROJECT /Users/nextus/Desktop/NextUs/AndroidOpenCV)


set(pathLIBOPENCV_JAVA ${pathPROJECT}/app/src/main/JniLibs/${ANDROID_ABI}/libopencv_java3.so)
