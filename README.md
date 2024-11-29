# Urdf5
<?xml version="1.0"?>
<robot name="prismatic_revolute_robot">

  <!-- Base Link -->
  <link name="base_link">
    <visual>
      <geometry>
        <box size="0.1 0.1 0.1"/>
      </geometry>
      <material name="blue"/>
    </visual>
  </link>

  <!-- Revolute Joint (Rotation around Z-axis) -->
  <joint name="joint1" type="revolute">
    <parent link="base_link"/>
    <child link="link1"/>
    <origin xyz="0 0 0.1" rpy="0 0 0"/>
    <axis xyz="0 0 1"/>
    <limit effort="100" velocity="1.0" lower="0" upper="1.57"/>
  </joint>

  <link name="link1">
    <visual>
      <geometry>
        <cylinder radius="0.05" length="0.2"/>
      </geometry>
      <material name="green"/>
    </visual>
  </link>

  <!-- Prismatic Joint (Translation along Z-axis) -->
  <joint name="joint2" type="prismatic">
    <parent link="link1"/>
    <child link="link2"/>
    <origin xyz="0 0 0.2" rpy="0 0 0"/>
    <axis xyz="0 0 1"/>
    <limit effort="100" velocity="1.0" lower="0" upper="0.5"/>
  </joint>

  <link name="link2">
    <visual>
      <geometry>
        <box size="0.05 0.05 0.2"/>
      </geometry>
      <material name="red"/>
    </visual>
  </link>

</robot>
