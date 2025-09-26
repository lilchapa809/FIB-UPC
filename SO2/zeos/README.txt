README text file (relevant information written)

Relevant Files: 
    system.c --> "First file read", contains important inizializations (IDT,GDT,TSS,...)
    user.c --> User code file, while(1)
    entry.S --> Handlers implementations, "ENTRY(name_handler)" 
                macro to declare a handler
    hardware.c --> It contains enable_int() function
    interrupt.c {
        --> SetIdt function to construct the IDT
        --> setInterruptHandler(int vector, void (*handler)(), int maxAccessibleFromPL);
            + int vector: Interruption position id 
            + void (*handler)(): name of the handler (declared in interrupt.h)
            + int maxAccessibleFromPL: Privilege Level (0=MAX, 3=USER)
    }
    interrupt.h --> Declaration of interrupt handlers