#include <mega16.h>
#include <delay.h>
#include <string.h>

void cmd();
void wdata();
int flag1=0,flag2=0,flag3=0,flag4=0;
unsigned char i;
unsigned char disp1[]="*WELCOME TO EVM*";
unsigned char disp2[]="PLEASE VOTE";
unsigned char disp3[]="!!!THANK YOU!!!";
unsigned char disp4[]="*** RESULTS ***";
unsigned char disp5[]="VOTING FINISHED";

void main()
{
DDRA=DDRB=DDRC=0b11111111;
DDRD=0b00000000;
PORTD=0b11111111;
PORTA=0x38;
cmd();
PORTA=0x06;
cmd();
PORTA=0x0E;
cmd();
PORTA=0x01;
cmd();
PORTA=0x80;
cmd();
for(i=0;i<16;i++)
{
PORTA=disp1[i];
wdata();
}
delay_ms(100);
PORTA=0x01;
cmd();

for(i=0;i<11;i++)
{
PORTA=disp2[i];
wdata();
}

do
  { 
       if(PIND.2==0)
       {
       PORTA=0x01;
       cmd();
       PORTA='A';
       wdata();
       delay_ms(50);
       PORTA=0x01;
       cmd();
       flag1++;
       for(i=0;i<15;i++)
       {
        PORTA=disp3[i];
        wdata();
       }           
       delay_ms(200);
       PORTA=0x01;
       cmd();
       for(i=0;i<11;i++)
       {
        PORTA=disp2[i];
        wdata();
       }
       }           
       else if(PIND.3==0)
      {
       PORTA=0x01;
       cmd();
       PORTA='B';
       wdata();
       delay_ms(50);
       PORTA=0x01;
       cmd();
       flag2++;
       for(i=0;i<15;i++)
       {
        PORTA=disp3[i];
        wdata();
       }           
       delay_ms(200);
       PORTA=0x01;
       cmd();
       for(i=0;i<11;i++)
       {
        PORTA=disp2[i];
        wdata();
       }
       }
       else if(PIND.4==0)
       {
       PORTA=0x01;
       cmd();
       PORTA='C';
       wdata();
       delay_ms(50);
       PORTA=0x01;
       cmd();
       flag3++;
       for(i=0;i<15;i++)
       {
        PORTA=disp3[i];
        wdata();
       }           
       delay_ms(200);
       PORTA=0x01;
       cmd();
       for(i=0;i<11;i++)
       {
        PORTA=disp2[i];
        wdata();
       }
       }
       else if(PIND.5==0)
       {
       PORTA=0x01;
       cmd();
       PORTA='D';
       wdata();
       delay_ms(50);
       PORTA=0x01;
       cmd();
       flag4++;
       for(i=0;i<15;i++)
       {
        PORTA=disp3[i];
        wdata();
       }           
       delay_ms(200);
       PORTA=0x01;
       cmd();
       for(i=0;i<11;i++)
       {
        PORTA=disp2[i];
        wdata();
       }
       }
       }while (PIND.0==0);
        PORTA=0x01;
        cmd();
        for(i=0;i<16;i++)
       {
        PORTA=disp5[i];
        wdata();
       }           
       delay_ms(200);
       PORTA=0x01;
       cmd();
       for(i=0;i<15;i++)
       {
        PORTA=disp4[i];
        wdata();
       }                
       do
         {
           PORTA=0x01;
           cmd();     
           PORTA='A';
           wdata();
           PORTA='=';
           wdata();
           switch(flag1)
           {
            case 1:
                   {
                    PORTA='1';
                    wdata();
                    break;
                   }
            case 2:
                   {
                    PORTA='2';
                    wdata();
                    break;
                   }
            case 3:
                   {
                    PORTA='3';
                    wdata();
                    break;
                   }
            case 4:
                   {
                    PORTA='4';
                    wdata();
                    break;
                   }
            case 5:
                   {
                    PORTA='5';
                    wdata();
                    break;
                   }
            case 6:
                   {
                    PORTA='6';
                    wdata();
                    break;
                   }
            case 7:
                   {
                    PORTA='7';
                    wdata();
                    break;
                   }
            case 8:
                   {
                    PORTA='8';
                    wdata();
                    break;
                   }
            case 9:
                   {
                    PORTA='9';
                    wdata();
                    break;
                   }
            default:
                  {
                   PORTA='0';
                   wdata();
                   break;
                  }    
           }
           PORTA=0x8a;
           cmd();     
           PORTA='B';
           wdata();
           PORTA='=';
           wdata();
           switch(flag2)
           {
            case 1:
                   {
                    PORTA='1';
                    wdata();
                    break;
                   }
            case 2:
                   {
                    PORTA='2';
                    wdata();
                    break;
                   }
            case 3:
                   {
                    PORTA='3';
                    wdata();
                    break;
                   }
            case 4:
                   {
                    PORTA='4';
                    wdata();
                    break;
                   }
            case 5:
                   {
                    PORTA='5';
                    wdata();
                    break;
                   }
            case 6:
                   {
                    PORTA='6';
                    wdata();
                    break;
                   }
            case 7:
                   {
                    PORTA='7';
                    wdata();
                    break;
                   }
            case 8:
                   {
                    PORTA='8';
                    wdata();
                    break;
                   }
            case 9:
                   {
                    PORTA='9';
                    wdata();
                    break;
                   }
            default:
                  {
                   PORTA='0';
                   wdata();
                   break;
                  }    
           }
           PORTA=0xC0;
           cmd();     
           PORTA='C';
           wdata();
           PORTA='=';
           wdata();
           switch(flag3)
           {
            case 1:
                   {
                    PORTA='1';
                    wdata();
                    break;
                   }
            case 2:
                   {
                    PORTA='2';
                    wdata();
                    break;
                   }
            case 3:
                   {
                    PORTA='3';
                    wdata();
                    break;
                   }
            case 4:
                   {
                    PORTA='4';
                    wdata();
                    break;
                   }
            case 5:
                   {
                    PORTA='5';
                    wdata();
                    break;
                   }
            case 6:
                   {
                    PORTA='6';
                    wdata();
                    break;
                   }
            case 7:
                   {
                    PORTA='7';
                    wdata();
                    break;
                   }
            case 8:
                   {
                    PORTA='8';
                    wdata();
                    break;
                   }
            case 9:
                   {
                    PORTA='9';
                    wdata();
                    break;
                   }
            default:
                  {
                   PORTA='0';
                   wdata();
                   break;
                  }    
           }
           PORTA=0xCa;
           cmd();    
           PORTA='D';
           wdata();
           PORTA='=';
           wdata();
           switch(flag4)
           {
            case 1:
                   {
                    PORTA='1';
                    wdata();
                    break;
                   }
            case 2:
                   {
                    PORTA='2';
                    wdata();
                    break;
                   }
            case 3:
                   {
                    PORTA='3';
                    wdata();
                    break;
                   }
            case 4:
                   {
                    PORTA='4';
                    wdata();
                    break;
                   }
            case 5:
                   {
                    PORTA='5';
                    wdata();
                    break;
                   }
            case 6:
                   {
                    PORTA='6';
                    wdata();
                    break;
                   }
            case 7:
                   {
                    PORTA='7';
                    wdata();
                    break;
                   }
            case 8:
                   {
                    PORTA='8';
                    wdata();
                    break;
                   }
            case 9:
                   {
                    PORTA='9';
                    wdata();
                    break;
                   }
            default:
                  {
                   PORTA='0';
                   wdata();
                   break;
                  }    
           }
           delay_ms(500);
           PORTA=0x01;
           cmd();        
         }while(PIND.1==0);
         
}

void cmd()
{
PORTB.0=0;
PORTB.1=0;
PORTB.2=1;
delay_ms(10);
PORTB.2=0;
}

void wdata()
{
PORTB.0=1;
PORTB.1=0;
PORTB.2=1;
delay_ms(10);
PORTB.2=0;
}

