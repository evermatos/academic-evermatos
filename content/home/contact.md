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
	{% include "webcontext/html_parts/nav.html" %}

<section class="py-5 container" id="contact">
		<div class="row">
			<div class="col-lg-8 mx-auto text-center">
				<h2 class="section-heading">Get In Touch!</h2>
				<hr style="max-width: 50px; border-width: 3px; border-color: #f05f40;" class="my-4">
				<p class="mb-5">
					Interdisciplinary Centre for Security, Reliability and Trust
					</br>
					29, avenue JF Kennedy L-1855 Luxembourg
					</br>
					Office: JFK Building, E02-224
				</p>
			</div>
		</div>
		<div class="row">
			<div class="col-lg-4 ml-auto text-center">
				<i class="fa fa-phone fa-3x mb-3 sr-contact"></i>
				<p>(+352) 46 66 44 6269</p>
			</div>
			<div class="col-lg-4 mr-auto text-center">
				<i class="fa fa-envelope fa-3x mb-3 sr-contact"></i>
				<div class="container">
					<div id="review_recaptcha"></div>
					<a id="email" href="#">Verify captcha to get e-mail</a>
				</div>

			</div>
		</div>
	</section>

	{% include "webcontext/html_parts/footer_short_content.html" %}

	<!-- Bootstrap core JavaScript
    ================================================== -->
	<!-- Placed at the end of the document so the pages load faster -->
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
					'sitekey' : '{% get_captcha_key %}',
					'theme' : 'light',
					callback : showEmail
				});
			}
		};
		function showEmail() {
			// ideally you would do server side verification of the captcha and then the server would return the e-mail
			name = 'willian';
			surname = 'tessarolunardi';
			domain = '@uni.lu';
			document.getElementById("email").innerHTML = name + '.' + surname + domain;
			$("#email").attr("href", 'mailto:' + name + '.' + surname + domain);
			$('#review_recaptcha').hide();
		}
	</script>