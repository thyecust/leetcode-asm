## 2690 https://leetcode.cn/problems/count-tested-devices-after-test-operations/

godbolt: https://godbolt.org/z/rjj5EEc7d

```assembly
main:                                   # @main
        push    rbp
        mov     rbp, rsp
        sub     rsp, 16
        lea     rdi, [rbp - 1]
        mov     rsi, qword ptr [rip + input@GOTPCREL]
        call    Solution::countTestedDevices(std::vector<int, std::allocator<int> >&)
        xor     eax, eax
        add     rsp, 16
        pop     rbp
        ret
Solution::countTestedDevices(std::vector<int, std::allocator<int> >&): # @Solution::countTestedDevices(std::vector<int, std::allocator<int> >&)
        push    rbp
        mov     rbp, rsp
        sub     rsp, 48
        mov     qword ptr [rbp - 8], rdi
        mov     qword ptr [rbp - 16], rsi
        mov     dword ptr [rbp - 20], 0
        mov     dword ptr [rbp - 24], 0
        mov     dword ptr [rbp - 28], 0
.LBB1_1:                                # =>This Inner Loop Header: Depth=1
        movsxd  rax, dword ptr [rbp - 28]
        mov     qword ptr [rbp - 40], rax       # 8-byte Spill
        mov     rdi, qword ptr [rbp - 16]
        call    std::vector<int, std::allocator<int> >::size() const
        mov     rcx, rax
        mov     rax, qword ptr [rbp - 40]       # 8-byte Reload
        cmp     rax, rcx
        jae     .LBB1_6
        mov     rdi, qword ptr [rbp - 16]
        movsxd  rsi, dword ptr [rbp - 28]
        call    std::vector<int, std::allocator<int> >::operator[](unsigned long)
        mov     eax, dword ptr [rax]
        sub     eax, dword ptr [rbp - 20]
        cmp     eax, 0
        jle     .LBB1_4
        mov     eax, dword ptr [rbp - 24]
        add     eax, 1
        mov     dword ptr [rbp - 24], eax
        mov     eax, dword ptr [rbp - 20]
        add     eax, 1
        mov     dword ptr [rbp - 20], eax
.LBB1_4:                                #   in Loop: Header=BB1_1 Depth=1
        jmp     .LBB1_5
.LBB1_5:                                #   in Loop: Header=BB1_1 Depth=1
        mov     eax, dword ptr [rbp - 28]
        add     eax, 1
        mov     dword ptr [rbp - 28], eax
        jmp     .LBB1_1
.LBB1_6:
        mov     eax, dword ptr [rbp - 24]
        add     rsp, 48
        pop     rbp
        ret
```
