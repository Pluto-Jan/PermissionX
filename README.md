# PermissionX
permission library
### 使用方法：

1：在project的build.gradle里面添加
  allprojects {
    repositories {
      maven { url 'https://jitpack.io' }
    }
  }
            
2：在app的build.gradle里面添加
   dependencies {
     implementation 'com.github.Pluto-Jan:PermissionX:Tag'
   }

3：使用方法：

// button按钮点击请求权限
Button.setOnClickListener {
            /**
             * 调用request方法请求权限
             * 参数（上下文，权限（多个参数以,隔开））
             * allGranted：是否同意权限
             * deniedList：拒绝权限后储存的集合
             * 
             */
            PermissionX.request(this, Manifest.permission.CALL_PHONE) { allGranted, deniedList ->
                if (allGranted) {
                    // 在这里处理同意权限后的操作
                } else {
                    Toast.makeText(this, "You denied $deniedList", Toast.LENGTH_SHORT).show()
                }
            }
        }
