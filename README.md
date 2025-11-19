# Stability-Analysis-using-Polar-Plot
## Aim:
To analyse the stability of the system having open loop transfer function, G(S)=10/(S(1+0.5S)(1+0.2S)) using polar plot and verify it using MATLAB. 
## Apparatus Required:
Computer with MATLAB software

## Theory:
![Image](https://github.com/user-attachments/assets/822550fa-b57c-41e2-9e7a-68032e4bb9c1)
![Image](https://github.com/user-attachments/assets/8e069a9f-4993-47fa-b93a-b379bb3ee613)

## Procedure:
	Open MATLAB software
	Open a new script file.
	Type the program.
	Save and Execute the program.
	Determine the gain crossover frequency, phase cross over frequency, gain margin and phase margin.
	Also determine the stability.

## Program: 

	num=[1]
	den = conv([1 0], conv([0.5 1], [0.2 1]));
	sys=tf(num,den)
	w=logspace(-1,2,1000);
	[mag phase]=bode(sys,w);
	mag=squeeze(mag);
	phase=squeeze(phase);
	theta=deg2rad(phase);
	polarplot(theta,mag,'LineWidth',1.5)
	[gm pm wpc wgc]=margin(sys)
	if (wpc>wgc)
	    disp('stable')
	elseif (wpc==wgc)
	    disp('marginally stable')
	else
	    disp('unstable')
	end

## Output:
<img width="1919" height="1199" alt="image" src="https://github.com/user-attachments/assets/3855f41e-3942-4f52-9faa-980f77b437d5" />

## Result:
Thus the polar plot for the given transfer function was drawn and verified using MATLAB. <br>
Gain margin = 0.70<br>
Phase Margin = -12<br>
Gain crossover frequency = 3.75<br>
Phase crossover frequency = 3.16<br>
The system is unstable
