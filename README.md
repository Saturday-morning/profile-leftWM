I changed the pre-loop section to instead of getting a single monitor, to get all the monitors by removing the grep and tac (which caused monitors to be in reverse order compared to leftwm-state -q -n -t $SCRIPTPATH/sizes.liquid). This is so I can set the monitor variable that's passed to the polybar command to the correct monitor (previously, it only got the first monitor and sent that to each). This fixes the highlighted tag being wrong. I got the correct monitor in-loop by using sed which was already a dependent of this script. However, sed expects it to be indexed at one so I created a new variable for that. I then set the 0-indexed variable at the end to that variable instead of recalculating index+1 (don't know if that's actually faster though). I also changed offsetx=$x to offset=$x since offsetx didn't work for my middle monitor which is index0 and a different size than the others. As far as I know, these changes are only an improvement and shouldn't break old setups.

The discription above is from the origin
--------------------------------

# 我的 LeftWM 主题配置备份
leftWM 更新太快了，我适应不了～（指的是更新之后忽然不会用了）

只留下一份存档
