<!DOCTYPE html>
<html>
    <head>
        <title>My web page</title>
    </head>
    <>
        
         
          <p>EXPERIMENT 1</p>
          <p>Performance of short transmission line, determination of voltage regulation and efficiency</p>
        <p> clc ; </p>
            <body> clear all; </body>p>
            <p> VRLL =220; VR = VRLL / sqrt (3); <\p>
            <p> Z = (0.15+%i*2*%pi*60*1.3263e-3) *40; <\p>
            <p> disp ( ' ( a ) ' ) <\p>
            <p> SR =304.8+ %i *228.6; // lagging power factor; receiving end power <\p>
            <p> IR = conj (SR) /(3* conj (VR)) ; //receiving end current <\p>
            <p> IS = IR; <\p>
            <p> VS = VR + Z*IR; //sending end voltage <\p>
            <p> VSLL = sqrt (3) * abs (VS) <\p>
            <p> SS = 3* VS* conj (IS) // sending end power <\p>
            <p> REG = ( VSLL - VRLL )/ VRLL *100 //regulation <\p>
            <p> Eff = real (SR)/ real (SS) *100 // efficiency <\p>
            <p> mprintf ( ' Sending end linevoltage = %f kV \n ' ,VSLL ) <\p>
            <p> mprintf ( ' Sending Apprent power = %f MVA \n ' ,SS) <\p>
            <p> mprintf ( ' Regulation = %f %% \n ' ,REG ) <\p>
            <p> mprintf ( ' Efficiency = %f %% \n ' ,Eff ) <\p>
            
               <p> EXPERIMENT 2</p>
               <p>Performance of short transmission line, determination of voltage regulation and efficiency</p>
                <p>SR =304.8 - %i *228.6; // leading power factor 
                    <p>IR = conj (SR) /(3* conj (VR)); IS = IR; 
                    <p>VS = VR + Z*IR; 
                    <p>VSLL = sqrt (3) * abs (VS) 
                    <p>SS = 3* VS* conj (IS) 
                    <p>REG = ( VSLL - VRLL )/ VRLL *100 
                    <p>Eff = real (SR)/ real (SS) *100 
                    <p>mprintf ( ' Sending end linevoltage = %f kV \n ' ,VSLL ) 
                    <p>mprintf ( ' Sending Apprent power = %f MVA \n ' ,SS) 
                    <p>mprintf ( ' Regulation = %f %% \n ' ,REG ) 
                    <p>mprintf ( ' Efficiency = %f %% \n ' ,Eff )
                    
                        <p> EXPERIMENT 3</p>  
                        <p>Performance of medium transmission line (nominal T),determination of voltage regulation and efficiency</p>
                        
<p>clc ; 
    <p>clear all; 
    <p>R =10; 
    <p>XL =20; 
    <p>Y= 4e-4; 
    <p>VRLL =66e3; 
    <p>PR =10000e3; 
    <p>pf =0.8; // change power factor of load 
    <p>VR =66e3/ sqrt (3); 
    <p>Z=R+%i*XL; 
    <p>IR=PR /( sqrt (3)* VRLL *pf); 
    <p>IR_COMPLEX =IR *( cos( acos (0.8) )-%i*sin( acos (0.8) )); 
    <p>VM=VR+ IR_COMPLEX *(Z /2) ; 
    <p>IC=%i*Y*VM; 
    <p>IS= IR_COMPLEX +IC; 
    <p>VS=VM+IS *(Z /2); 
    <p> [ VS_abs , Phase_VS ]= polar (VS); 
    <p> [ IS_abs , Phase_IS ]= polar (IS); 
    <p>VS_abs ; 
    <p>IS_abs 
    <p>VSLL =VS* sqrt (3) ; 
    <p>VSLL_abs = abs ( VSLL ) /1000 
    <p>PHASE_DIFF = Phase_VS - Phase_IS ; 
    <p>SendingEnd_PF =cos( PHASE_DIFF ) 
    <p>PS =3* abs (VS)*abs(IS)* cos ( PHASE_DIFF ); 
    <p>EFF =( abs (PR)/ abs (PS)) *100 
    <p>REG = 100*(( abs ( VSLL ) - abs ( VRLL )))/ abs ( VRLL ) 
    <p>mprintf ( ' Sending end Current = %f A \n ' ,IS_abs ) 
    <p>mprintf ( ' Sending end Line Voltage = %f kV \n ' ,VSLL_abs ) 
    <p>mprintf ( ' Sendingend Power factor = %f \n ' ,SendingEnd_PF ) 
    <p>mprintf ( ' Efficiency = %f %% \n ' , EFF ) 
    <p>mprintf ( ' Regulation = %f %% \n ' , REG )
    
        <p> EXPERIMENT 4</p>  
        <p>Performance of medium transmission line (nominal-π),determination of voltage regulation and efficiency</p>
        <p>clc 
            <p>clear all 
            <p>R = 10; 
            <p>XL = 50; 
            <p>Y = 10e-4; 
            <p>f =50; 
            <p>PR= 20e6; 
            <p>VRLL = 66e3; 
            <p>pf= 0.9; 
            <p>Z=R+%i*XL; 
            <p>VR = VRLL / sqrt (3); 
            <p>IR=PR /( sqrt (3)* VRLL *pf); 
            <p>IR_COMPLEX =IR *( cos( acos (pf))-%i* sin ( acos (pf))); 
            <p>IC1 =%i*Y/2* VR; 
            <p>IL = IR_COMPLEX + IC1; 
            <p>VS = VR + IL*Z; 
            <p>IC2 = %i*Y/2* VS; 
            <p>IS=IL + IC2 
            <p> [ VS_abs , Phase_VS ]= polar (VS); 
            <p> [ IS_abs , Phase_IS ]= polar (IS); 
            <p>VS_abs ; 
            <p>IS_abs ; 
            <p>VSLL =VS* sqrt (3) ; 
            <p>VSLL_abs = abs ( VSLL ) /1000 
            <p>PHASE_DIFF = Phase_VS - Phase_IS ; 
            <p>SendingEnd_PF =cos( PHASE_DIFF ); 
            <p>PS =3* abs (VS)*abs(IS)* cos ( PHASE_DIFF ) 
            <p>EFF =( abs (PR)/ abs (PS)) *100 
            <p>REG = 100*(( abs ( VSLL ) - abs ( VRLL )))/ abs ( VRLL ) 
            <p>mprintf ( ' Sending end Current = %f A \n ' ,IS_abs ) 
            <p>mprintf ( ' Sending end Line Voltage = %f kV \n ' ,VSLL_abs ) 
            <p>mprintf ( ' Sending end Power factor = %f \n ' ,SendingEnd_PF ) 
            <p>mprintf ( ' Efficiency = %f %% \n ' , EFF ) 
            <p>mprintf ( ' Regulation = %f %% \n ' , REG )
            
                <p> EXPERIMENT 5</p>  
                <p>FORMATION OF Y-BUS FOR POWER SYSTEM BY INSPECTION METHOD</p>
                <p>clc 
                    <p>clear 
                    <p>// F T Z HLC 
                    <p>linedata = [1 2 0.2*(%i) 0.03*(%i); 
                    <p>1 4 0.25*(%i) 0.025*(%i); 
                    <p>2 3 0.4*(%i) 0.02*(%i); 
                    <p>2 4 0.5*(%i) 0.015*(%i); 
                    <p>3 4 0.2*(%i) 0.01*(%i)]; 
                    <p>Sh=[4 0.02*(%i)]; // b-, 
                    <p>from_bus=real(linedata(:,1)); // 
                    <p>to_bus=real(linedata(:,2)); // 
                    <p>Z=linedata(:,3); // 
                    <p>HLC=linedata(:,4); 
                    <p>nbus=max(max(from_bus),max(to_bus)); 
                    <p>e=length(from_bus); 
                    <p>Ybus=zeros(nbus, nbus); 
                    <p>for k=1:e // k takes values from 1 to maximum line number e 
                    <p>p=from_bus(k); 
                    <p>q=to_bus(k);  
                    <p>z=Z(k); 
                    <p>hlc=HLC(k);  
                    <p>y=1/z; // y = reciprocal of z 
                    <p>Ybus(p,q)=Ybus(p,q)-y;  
                    <p>Ybus(q,p)=Ybus(p,q);  
                    <p>// formation of the diagonal elements 
                    <p>Ybus(p,p)=Ybus(p,p)+y+hlc;  
                    <p>Ybus(q,q)=Ybus(q,q)+y+hlc;  
                    <p>end 
                    <p>// Addition of shunt admittance data 
                    <p>// Bus no. at which shunt compensation is provided 
                    <p>p=Sh(1,1); 
                    <p>sh_compensation=Sh(1,2); 
                    <p>p=real(p); 
                    <p>Ybus(p,p)=Ybus(p,p)+sh_compensation ; 
                    <p>Ybus 
                    <p>disp(Ybus)

                        <p> EXPERIMENT 6</p> 
                        <p>FORMATION OF Y-BUS FOR POWER SYSTEMWITHOUT MUTUAL COUPLING, BY SINGULAR TRANSFORMATION METHOD</p>
                        <p>clc 
                            <p>clear 
                            <p>// F T Z HLC 
                            <p>linedata = [1 2 0.2*(%i) 0.03*(%i); 
                            <p>1 4 0.25*(%i) 0.025*(%i); 
                            <p>2 3 0.4*(%i) 0.02*(%i); 
                            <p>2 4 0.5*(%i) 0.015*(%i); 
                            <p>3 4 0.2*(%i) 0.01*(%i)]; 
                            <p>from_bus=real(linedata(:,1)); 
                            <p>to_bus=real(linedata(:,2)); 
                            <p>Z=linedata(:,3); 
                            <p>HLC=linedata(:,4); 
                            <p>nbus=max(max(from_bus),max(to_bus));  
                            <p>e=length(from_bus);  
                            <p>a=zeros(e,nbus);  
                            <p>Zpri=zeros(e,e);  
                            <p>for k=1:e // k takes values from 1 to maximum line number e 
                            <p>p=from_bus(k,1); 
                            <p>q=to_bus(k,1); 
                            <p>z=linedata(k,3); 
                            <p>//Formation of Bus Incidence matrix 
                            <p>a(k,p)=1; 
                            <p>a(k,q)=-1; 
                            <p>Zpri(k,k)=z; 
                            <p>end 
                            <p>Ypri=inv(Zpri);  
                            <p>Ybus=a'*Ypri*a; 
                            <p>//Addition of Half Line Charging Admittance to diagonal elements of Ybus 
                            <p>for k=1:1:e 
                            <p>p=from_bus(k,1); 
                            <p>q=to_bus(k,1); 
                            <p>hlc=HLC(k,1); 
                            <p>Ybus(p,p)=Ybus(p,p)+hlc; 
                            <p>Ybus(q,q)=Ybus(q,q)+hlc; 
                            <p>end 
                            <p>disp(Ybus)

                                <p> EXPERIMENT 7</p> 
                                <p>ECONOMIC DISPATCH IN POWER SYSTEM NEGLECTING LOSSES</p>

                                <p>clear ; 
                                    <p>clc ; 
                                    <p>n= input ( ' Enter number of units:'); 
                                    <p>F= input ( 'Enter the cost coefficient in matrix form :'); 
                                    <p>constraint = input ( ' Enter min and max values of P for all units : ' ); 
                                    <p>pd= input ( ' Enter total demand : ' ); 
                                    <p>a=F(: ,1);b=F(: ,2);c=F(: ,3); 
                                    <p>Pmin = constraint (: ,1); 
                                    <p>Pmax = constraint (: ,2); 
                                    <p>chk = zeros (n ,1) ; 
                                    <p>rem =1; 
                                    <p>while rem ==1 
                                    <p>sx =0; sy =0; 
                                    <p>for i =1: n 
                                    <p>if i~= chk (i) 
                                    <p>sx=sx+b(i) /(2* a(i)); 
                                    <p>sy=sy +1/(2* a(i)); 
                                    <p>end 
                                    <p>end 
                                    <p>lamda =( pd+sx)/sy; 
                                    <p>sch =0; 
                                    <p>for i =1: n 
                                    <p>if i~= chk (i) 
                                    <p>P(i)=( lamda -b(i)) /(2* a(i)); 
                                    <p>if P(i)<Pmin (i)|P(i)>Pmax (i) 
                                    <p>if P(i)< Pmin (i) 
                                    <p>P(i)= Pmin (i); 
                                    <p>else 
                                    <p>P(i)= Pmax (i); 
                                    <p>end 
                                    <p>pd=pd -P(i); 
                                    <p>chk (i)=i; 
                                    <p>sch = sch +1; 
                                    <p>end 
                                    <p>end 
                                    <p>if sch ==0 
                                    <p>rem =0; 
                                    <p>else 
                                    <p>rem =1; 
                                    <p>end 
                                    <p>end 
                                    <p>end 
                                    <p>disp ( 'The optimum schedule is : ' )
                                    <p>disp ( %io (2) ,P)
                                    
                    


































             
        
            
        </p>
    </body>
</html>
