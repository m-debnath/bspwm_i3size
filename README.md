# i3_resize for bspwm
## BSPWM's resizing suckssss
To use i3 like resize in bspwm in linux, proceed with these commands :

    git clone https://github.com/zim0369/bspwm_i3size $HOME/.config/bspwm/
    chmod +rwx $HOME/.config/bspwm/bspwm_i3size/*
In your sxhkdrc :

    # contract a window by moving one of its side inward
    alt + {h,j,k,l}
    	bspc node -z {right -20 0,top 0 20,bottom 0 -20,left 20 0}
    
    # expand a window by moving one of its side outward
    alt + shift + {h,j,k,l}
    	bspc node -z {left -20 0,bottom 0 20,top 0 -20,right 20 0}
Replace these lines with :

    # i3 like resizing
    alt + h
        /bin/sh $HOME/.config/bspwm/i3_resize/shrinkx.sh
    alt + l
        /bin/sh $HOME/.config/bspwm/i3_resize/expandx.sh
    alt + k
        /bin/sh $HOME/.config/bspwm/i3_resize/shrinky.sh
    alt + j
        /bin/sh $HOME/.config/bspwm/i3_resize/expandy.sh
