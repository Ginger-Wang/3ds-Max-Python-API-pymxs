import MaxPlus,pymxs
rt = pymxs.runtime
mp = MaxPlus

source = rt.Point(position = rt.Point3(20,0,20))
target = rt.Point(position = rt.Point3(-20,0,20))

iNode = mp.INode.GetINodeByName(target.name)
controlList = mp.ControlList()
controlList.Append(mp.Factory.CreateRotationController(mp.ClassIds.Euler_XYZ))
controlList.Append(mp.Factory.CreateRotationController(mp.ClassIds.Orientation_Constraint))
control = mp.Factory.CreateRotationController(mp.ClassIds.rotation_list)
for index in range(controlList.GetCount()):
  control.AssignController(controlList[index],index)

targetTMController = iNode.GetTMController()
targetTMController.SetRotationController(control)

rotationControl = rt.getPropertyController(target.controller,"Rotation")
constraints = None
for i in rotationControl:
  if "Orientation_Constraint" in str(i):
    constraints = i
interFace = constraints.constraints
interFace.appendTarget(source,100.0)
