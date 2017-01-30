// set these values to match the comb dimensions that you intend to use with this casting/running tray
// Use the comb-generator to get the values or design your own custom comb

gel_width = 90;
gel_length = 110;

comb_depth = 12; // excluding the grab-handle, i.e. just the teeth.
gel_thickness_below_comb = 2;

wall_thickness = 5;

gel_depth = 10; // for rendering the demo gel below

tray_height = wall_thickness + comb_depth + gel_thickness_below_comb + 10;
tray_outside_dims = [gel_width + (2 * wall_thickness), gel_length, tray_height];
tray_inside_dims = [gel_width, 1.1 * gel_length, 1.1 * tray_height - wall_thickness];

comb_rest_level = comb_depth + wall_thickness + gel_thickness_below_comb;

difference() {
    // the gel tray
    cube(tray_outside_dims);
    translate([wall_thickness, -1, wall_thickness]) cube(tray_inside_dims);
    
    // notch for comb
    translate([-5, gel_length - 10, comb_rest_level]) cube([1.1 * (tray_outside_dims[0]), 3.5, 11]);
}

// demo gel
% color("LightCyan", 0.5 ) {
    translate([wall_thickness, 0, wall_thickness]) cube([gel_width, gel_length, gel_depth]);
}

// demo comb -- delete from here ... 
color("LightCoral", 1 ) {
    translate([wall_thickness + 3, gel_length - 6.7, comb_rest_level-comb_depth]) rotate(90, [1, 0, 0]) import("Geltank Comb - 12 mm x 6+2.stl");
}
// ... to here before rendering!


// If you plan to buy acrylic sheets rather than 3D-print this out then
// check the console ouput for the sheet dimensions to order.
echo(["Polycarbonate sheet ordering instructions:"]);
echo(["Bottom Panel (x1) at ", gel_length , " mm x ", gel_width, " mm."]);
echo(["Side Panels (x2) at ", gel_length , " mm x ", tray_height, " mm."]);
echo(["Cut notch 10 mm from one end, make it 3.5 mm width and 10 mm deep"]);
