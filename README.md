# 283_3

This is an individual assignment finished by myself.

For CPUID leaf node %eax=0x4FFFFFFF:
◦Return the total number of exits (all types) in %eax
•For CPUID leaf node %eax=0x4FFFFFFE:
◦Return the high 32 bits of the total time spent processing all exits in %ebx
◦Return the low 32 bits of the total time spent processing all exits in %ecx
▪%ebx and %ecx return values are measured in processor cycles, across all VCPUs
•For CPUID leaf node %eax=0x4FFFFFFD:
◦Return the number of exits for the exit number provided (on input) in %ecx
▪This value should be returned in %eax 
•For CPUID leaf node %eax=0x4FFFFFFC:
◦Return the time spent processing the exit number provided (on input) in %ecx
▪Return the high 32 bits of the total time spent for that exit in %ebx
▪Return the low 32 bits of the total time spent for that exit in %ecx

For this assignment, the leaf chosen is %eax=0x4FFFFFFD and 0x4FFFFFFC:

1.modify the vmx.c functions, made changes in the vmx_handle_exit function to calculate the number of exisit by using atomic varibale
2.impletement the leaf function of 0x4ffffffe
3.Test the modified kernel by using kvm

Question:
1.Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there 
more exits performed during certain VM operations? Approximately how many exits does a full VM 
boot entail?
-It increases at a stable rate, and there are more exits performed. There are around 5 million exits when a full VMboot entail.
2.Of the exit types defined in the SDM, which are the most frequent? Least?
-Control Register Accesses is the most frequent; while MOV DR is the least frequent.
