@startuml
title Nhóm 1 - Xác thực & Tài khoản
left to right direction

actor "Khách hàng" as KH
actor "SMS Gateway" as SMS

rectangle "Xác thực & Tài khoản" {
    usecase "UC01\nĐăng ký tài khoản" as UC01
    usecase "UC02\nXác thực OTP" as UC02
    usecase "UC03\nĐăng nhập hệ thống" as UC03
    usecase "UC04\nKhôi phục mật khẩu" as UC04
    usecase "UC05\nQuản lý hồ sơ cá nhân" as UC05
    usecase "UC06\nĐổi mật khẩu" as UC06
    usecase "UC22\nPhát tin nhắn OTP\nvà thông báo SMS" as UC22
}

KH --> UC01
KH --> UC02
KH --> UC03
KH --> UC04
KH --> UC05
KH --> UC06

SMS --> UC22

UC01 ..> UC02 : <<include>>
UC04 ..> UC02 : <<include>>
UC02 ..> UC22 : <<include>>

@enduml
