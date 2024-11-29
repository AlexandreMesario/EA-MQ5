

#include <Trade\Trade.mqh>  
CTrade meutrade;  


// A função tem que arrastar uma ordem com a distandia de 500 ponto e a outra com 1000 pontos 
         
void OnTick()                                                               
  {

   double precoatual = SymbolInfoDouble(_Symbol, SYMBOL_LAST);

  double precoentrada = PositionGetDouble(POSITION_PRICE_OPEN);

   

 
 
        double ask, bid;
            
          bid = SymbolInfoDouble(_Symbol, SYMBOL_BID);
          ask = SymbolInfoDouble(_Symbol, SYMBOL_ASK); 



//-----------------------------------------------
                     
    if ( PositionsTotal()==0 && OrdersTotal()==0)
 
      {
                       
                 
        meutrade.BuyStop(0.10,ask+(500*_Point),_Symbol,0,0);   meutrade.SellStop(0.10,bid-(500*_Point),_Symbol,0,0);            
         meutrade.BuyStop(0.10,ask+(1000*_Point),_Symbol,0,0);   meutrade.SellStop(0.10,bid-(1000*_Point),_Symbol,0,0);                        
      } 
      

 //   processTrailing();

              
}







