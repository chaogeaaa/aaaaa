<!DOCTYPE html>
<html>
	<head>
		<meta charset="utf-8" />
		<title></title>
		<script src="js/jquery-1.8.3.min(1).js"></script>
		<script>
			$(function(){
				$.ajax({
					url:'ajax.xml',
					type:'GET',
					dataType:'xml',
					timeout:'1000',
					cache:'false',
					success:function(xml){
						var frag=$("<ul/>");
						$(xml).find('student').each(function(i){
							var id=$(this).children('id');
							var id_value=id.text();
							email=$(this).attr('email');
							frag.append("<li>"+id_value+"-"+email+"</li>");
						})
						frag.appendTo("#load");
					}
				})
			})
		</script>
	</head>
	<body>
		<div id="load"></div>
	</body>
</html>
