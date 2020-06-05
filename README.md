打包jar包
task makeJar(type: Copy) {
        //删除存在的
        delete 'build/libs/myjar.jar'
        //设置拷贝的文件
        from('build/intermediates/aar_main_jar/release/')
        //打进jar包后的文件目录
        into('build/libs/')
        //将classes.jar放入build/libs/目录下
        //include ,exclude参数来设置过滤
        //（我们只关心classes.jar这个文件）
        include('classes.jar')
        //重命名
        rename ('classes.jar', 'mylibrary.jar')
    }
makeJar.dependsOn(build)

class jar包打包成dex jar包命令
在SDK的Build-tools里面
 .\dx.bat --dex --output= .\my_library_dx.jar .\my_library.jar
 
参考网站:https://blog.51cto.com/13952501/2169865
 
 
外部jar包和app模块使用同一接口规范实现，注意打包jar不能打包接口，可通过依赖其它包含该接口的库来实现，接口包名需一致，实现类包名需一致


--------------------------------git命令---------------------------------------------------------------------------
git remote rm origin
git branch --set-upstream-to origin/master
git pull --allow-unrelated-histories


