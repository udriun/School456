# School456

#-------------------------------------------------------------------------------
# Name:        module1
# Purpose:
#
# Author:      udriu
#
# Created:     30/09/2018
# Copyright:   (c) udriu 2018
# Licence:     <your licence>
#-------------------------------------------------------------------------------

import arcpy
from arcpy import env

env.overwriteOutput = Ture

env.workspace = "D:\\GEOS456\\Mod2Act1\\Geodatabase\\456_Mod02Act1.gdb"


arcpy.Buffer_analysis("hospitals","hospitals_buff",10000,"#","#","ALL","","")

clip_feat = "hospitals_buff"

clip_in = "bike_routes"

arcpy.Clip_analysis(clip_in,clip_feat,"bike_routes_Clip")

print arcpy.GetMessages()
