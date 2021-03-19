import pymxs
rt = pymxs.runtime

source = rt.Point(Name = "sourcePoint",Box = True,cross = False,position = rt.Point3(20,0,20))
target = rt.Point(Name = "targetPoint",Box = True,cross = False,position = rt.Point3(20,0,20))

roList = rt.rotation_list()
roConstraint = rt.Orientation_Constraint()
rt.SetPropertyController(source.controller,"Rotation",roList)
roControl = rt.getPropertyController(source.controller,"Rotation")
rt.SetPropertyController(roControl,"Available",roConstraint)
constraint = roConstraint.constraints
constraint.appendTarget(target,100.0)
