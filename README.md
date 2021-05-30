# tinify
Tinify is image compresser from tiny png. This library create for Codeigniter 3

#Installation
for installation follow the step bellow
<pre>git clone https://github.com/is01252/tinify.git</pre>
move file Tiny_png.php on directory <b>libraries/</b>

#Using
On controller file create this function.
for example this function is for resize image
<pre>
public function resize_tinify($image)
	{
		$site = $this->site_model->get_site_data()->row_array();
		$this->load->library('tiny_png', array('api_key' => 'YOUR_API_KEY'));

		$path 		= './uploads/images/'.$image;
		$new_path 	= './uploads/fasilitas/thumbs/'.$image;
		$method 	= 'thumb';
		$width 		= 150;
		$height 	= 150;

		// $method (string) method of resize image: 'scale', 'fit', 'cover', 'thumb' 
		$this->tiny_png->fileResize($path, $new_path, $method, $width, $height);
	}
</pre>
