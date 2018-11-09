+++
# Custom widget.
# An example of using the custom widget to create your own homepage section.
# To create more sections, duplicate this file and edit the values below as desired.
widget = "custom"
active = true
date = 2016-04-20T00:00:00

# Note: a full width section format can be enabled by commenting out the `title` and `subtitle` with a `#`.
title = "Contato"
subtitle = ""

# Order that this section will appear in.
weight = 70

+++

<div class="container">
					<div id="review_recaptcha"></div>
					<a id="email" href="#">Verifique o captcha para visualizar o e-mail</a>
</div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
<!-- <script
		src="//maxcdn.bootstrapcdn.com/bootstrap/3.3.0/js/bootstrap.min.js"></script> -->
<script src="{% static 'webcontext/js/bootstrap.min.js' %}"></script>
<script src="{% static 'webcontext/js/form_comment.js' %}"></script>
<script src="https://www.google.com/recaptcha/api.js?onload=onloadCallback&render=explicit"></script>
<script type="text/javascript">
		var onloadCallback = function() {
			if ($('#review_recaptcha').length) {
				grecaptcha.render('review_recaptcha', {
					'sitekey' : '6LdcpnkUAAAAAIbbjTLpmgntQ8TThBEQrAhL_Zjw',
					'theme' : 'light',
					callback : showEmail
				});
			}
		};
		function showEmail() {
			// ideally you would do server side verification of the captcha and then the server would return the e-mail
			name = 'everton';
			surname = 'matos';
			domain = '@imed.edu.br';
			document.getElementById("email").innerHTML = name + '.' + surname + domain;
			$("#email").attr("href", 'mailto:' + name + '.' + surname + domain);
			$('#review_recaptcha').hide();
		}
</script>