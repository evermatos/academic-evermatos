+++
# Contact widget.
widget = "contact"
active = true
date = 2016-04-20T00:00:00

title = "Contact"
subtitle = ""

# Order that this section will appear in.
weight = 70

# Automatically link email and phone?
autolink = true

# Email form provider
#   0: Disable email form
#   1: Netlify (requires that the site is hosted by Netlify)
#   2: formspree.io
email_form = 0
+++

<script src='https://www.google.com/recaptcha/api.js'></script>
<div class="g-recaptcha" data-sitekey="6LdcpnkUAAAAAIbbjTLpmgntQ8TThBEQrAhL_Zjw"></div>


<section class="py-5 container" id="contact">
			<div class="col-lg-4 mr-auto text-center">
				<i class="fa fa-envelope fa-3x mb-3 sr-contact"></i>
				<div class="container">
					<div id="review_recaptcha"></div>
					<a id="email" href="#">Verify captcha to get e-mail</a>
				</div>
			</div>
		</div>
	</section>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.12.4/jquery.min.js"></script>
	<script src="{% static 'webcontext/js/bootstrap.min.js' %}"></script>
	<script src="{% static 'webcontext/js/form_comment.js' %}"></script>
	<script src="https://www.google.com/recaptcha/api.js?onload=onloadCallback&render=explicit"></script>
	<script type="text/javascript">
		var onloadCallback = function() {
			if ($('#review_recaptcha').length) {
				grecaptcha.render('review_recaptcha', {
					'data-sitekey' : '{% get_captcha_key %}',
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