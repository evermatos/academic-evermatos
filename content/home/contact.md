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
<script src="https://www.google.com/recaptcha/api.js?onload=onloadCallback&render=explicit"></script>
<script type="text/javascript">
		var onloadCallback = function() {
			if ("$g-recaptcha-response".length) {
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
			"$g-recaptcha-response".hide();
		}
	</script>