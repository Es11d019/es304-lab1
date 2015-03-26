# es304-lab1
8 Led гэрлийг 2 товчлуураар удирдах. Эхний товчлуурыг дархад led нэг нэгээр асах харин хоёрдох товчлуурыг дархад led нэг нэгээр унтраж байх код. 
#include "D:\lesson\2015_havar\microconterllor\es304 labs\lab1\lab1.h"

int j=0,c=0,data[9]={0x00,0x01,0x03,0x07,0x0f,0x1f,0x3f,0x7f,0xff};

void main()
{

set_tris_d(0x00);
set_tris_b(0xff);

   setup_adc_ports(NO_ANALOGS);
   setup_adc(ADC_OFF);
   setup_psp(PSP_DISABLED);
   setup_spi(FALSE);
   setup_timer_0(RTCC_INTERNAL|RTCC_DIV_1);
   setup_timer_1(T1_DISABLED);
   setup_timer_2(T2_DISABLED,0,1);
setup_comparator(NC_NC_NC_NC);
   setup_vref(FALSE);

   // TODO: USER CODE!!
   output_d(data[0]);
   
      while(1){    
      
      if(input(PIN_B0)){
      delay_ms(70);
         if(j<8)
         {
         j++;
         output_d(data[j]); 
      }}
       
 
      if(input(PIN_B1)){
      delay_ms(70);
         if(j<1){
         j=0;
         }
         else
         j--;
         output_d(data[j]);
         }   
     }
        
}
