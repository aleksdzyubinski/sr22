<?php

if (!empty($_POST) &&
    isset($_POST['firstname']) &&
    isset($_POST['lastname']) &&
    isset($_POST['zip']) &&
    isset($_POST['phone']) &&
    isset($_POST['day']) &&
    isset($_POST['email'])
) {

  if ( isset($_POST['firstname']) && isset($_POST['lastname']) ) $fullname = htmlspecialchars($_POST['firstname']) . ' ' .htmlspecialchars($_POST['lastname']);
  if ( isset($_POST['zip']) ) $zip = htmlspecialchars($_POST['zip']);
  if ( isset($_POST['phone']) ) $phone = htmlspecialchars($_POST['phone']);
  if ( isset($_POST['day']) && isset($_POST['month']) && isset($_POST['year']) ) $birthday = htmlspecialchars($_POST['day']) . ' ' .date("F", mktime(0, 0, 0,htmlspecialchars($_POST['month']), 10)) . ', ' .htmlspecialchars($_POST['year']);
  if ( isset($_POST['email']) ) $email = htmlspecialchars($_POST['email']);

  //$monthNum = 5;
  //$monthName = date("F", mktime(0, 0, 0, $monthNum, 10)); 
  //if ( isset($_POST['non-owner']) ) $non_owner = $_POST['non-owner'];
  //echo 'here1';
  //define('__ROOT__', dirname(dirname(__FILE__))); 
  require_once(dirname(__FILE__).DIRECTORY_SEPARATOR.'lib'.DIRECTORY_SEPARATOR.'PHPMailerAutoload.php');
  //require_once "/lib/PHPMailerAutoload.php";

  //PHPMailer Object
  $mail = new PHPMailer;

  $mail->IsSMTP();
  $mail->Host = 'smtpout.secureserver.net';
  $mail->SMTPAuth = true;
  $mail->Username = "monica@mis-insurance.com";
  $mail->Password = "Matin1981";

  $mail->Port = 465;
  $mail->SMTPSecure = 'ssl';

  //From email address and name
  $mail->From = 'form@mis-insurance.com';
  $mail->FromName = 'MIS Insurance';

  //To address and name
  $mail->addAddress("sales@mis-insurance.com", "Sales");

  /* For test
  $mail->addAddress("paul.ryazanov@gmail.com", "Paul");
  */
  //$mail->addAddress("recepient1@example.com"); //Recipient name is optional
  //CC and BCC
  //$mail->addCC("cc@example.com");
  //$mail->addBCC("bcc@example.com");
  //$mail->addCC('cesar@mis-insurance.com', 'Cesar');
  //$mail->addCC('adriann@mis-insurance.com', 'Adriann');
//  $mail->addCC('julie@mis-insurance.com', 'Julie');
  //$mail->addCC('matinsabz@gmail.com', 'Matinsabz');
//  $mail->addCC('3108010921@mms.att.net', '3108010921');
//  $mail->addCC('Bryce@mis-insurance.com', 'Bryce');
//  $mail->addCC('Jackie@mis-insurance.com', 'Jackie');
//  $mail->addCC('melissa@mis-insurance.com', 'Melissa');
  //$mail->addCC('john@mis-insurance.com', 'John');
  $mail->addCC('3108010921@mms.att.net', 'MMS');
  /* For Test
  $mail->addCC('bompok@gmail.com', 'Sergiy');
  $mail->addCC('yura@magecloud.net', 'Yura');
  $mail->addCC('alex@magecloud.net', 'Alex');
  */
//  $mail->addCC('yura@magecloud.net', 'Yura');
//  $mail->addCC('paul.ryazanov@gmail.com', 'Paul');

  //Address to which recipient will reply
  $mail->addReplyTo($email, "Reply");
  //Send HTML or Plain Text email
  $mail->isHTML(true);

  $mail->Subject = "SR22 quote from Landing page #2";
  $mail->Body = "<h3>Instant Quote</h3><p>Full Name: ".$fullname."</p>"
  ."<p>Zip Code: ".$zip."</p>"
  ."<p>Phone: ".$phone."</p>"
  ."<p>Date of Birth: ".$birthday."</p>"
  ."<p>Email: ".$email."</p>"
  ;

  if(isset($_POST['non-owner']) &&
     $_POST['non-owner'] == 'true')
  {
      $mail->Body .= "<p>I need a non-owner policy</p>";
  }
  else
  {
      $mail->Body .= "<p>I don't need a non-owner policy</p>";
  }
  $mail->AltBody = "";//"This is the plain text version of the email content";

  if(!$mail->send())
  {
      echo "Mailer Error: " . $mail->ErrorInfo;
  }
  else
  {
      //echo "Message has been sent successfully";
      //header("Location: http://theme.com/MIS/thank-you.php"); /* Redirect browser */
      header("Location: http://sr22.mis-insurance.com/thank-you.php");
      exit();
  }
}
?>
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <!-- The above 3 meta tags *must* come first in the head; any other head content must come *after* these tags -->
    <title>MIS</title>

    <!-- Bootstrap -->
    <link href="assets/css/bootstrap.min.css" rel="stylesheet">
    <link href="assets/css/style.css" rel="stylesheet">
    <!-- HTML5 shim and Respond.js for IE8 support of HTML5 elements and media queries -->
    <!-- WARNING: Respond.js doesn't work if you view the page via file:// -->
    <!--[if lt IE 9]>
      <script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
      <script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
    <![endif]-->

  </head>

  <body>
<!-- Google Tag Manager -->
<noscript><iframe src="//www.googletagmanager.com/ns.html?id=GTM-KR3FML" height="0" width="0" style="display:none;visibility:hidden"></iframe></noscript>
<script>(function(w,d,s,l,i){w[l]=w[l]||[];w[l].push({'gtm.start':new Date().getTime(),event:'gtm.js'});var f=d.getElementsByTagName(s)[0],
j=d.createElement(s),dl=l!='dataLayer'?'&l='+l:'';j.async=true;j.src='//www.googletagmanager.com/gtm.js?id='+i+dl;f.parentNode.insertBefore(j,f);
})(window,document,'script','dataLayer','GTM-KR3FML');</script>
<!-- End Google Tag Manager -->
    <header class="header">
      <div class="container">
        <a class="brand" href="/" title="Matin Insurance Services"><img alt="Matin Insurance Services" src="assets/img/logo.png"/></a>
        <div class="header-contact">
          <p>Free Quote online <em>or</em> call</p>
          <a class="phone" href="tel:877-611-4647">877-611-4647</a>
        </div>
      </div>
    </header>
    <div class="jumbotron white">
      <div class="container">
        <h1>SR22 & Non Owner Operator Insurance As Low As <span class="text-muted">$12/month</span></h1>
        <div class="row">
        <div class="col-md-6">
          <p>We offer the fastest and most affordable SR-22 Insurance in California. Our rates start as low as $12/month. Get an instant quote. Purchase. Print your certificate & reinstate your license the same day.</p>
          <ul>
            <li>Instant SR22 filing with the DMV</li>
            <li>5 star Yelp Reviews</li>
            <li>No Hidden fees</li>
            <li>Print Your SR22 Certificate Instantly</li>
          </ul>
          <p class="call-now">Call Now to Speak to An Agent</p>
          <a class="phone phone-bottom" href="tel:877-611-4647">877-611-4647</a>
        </div>
        <div class="col-md-6">
        <div class="sendEmail">
          <form class="form-horizontal" method="post"  action="<?php echo $_SERVER['PHP_SELF']; ?>" >
            <h2>Receive An Instant Quote</h3>
            <div class="form-group">
              <label for="inputFirstName" class="col-sm-3 control-label">First Name</label>
              <div class="col-sm-9">
                <input type="text" class="form-control" id="inputFirstName" name="firstname" data-validation="alphanumeric" data-validation-allowing=" " placeholder="First Name">
              </div>
            </div>
            <div class="form-group">
              <label for="inputLastName" class="col-sm-3 control-label">Last Name</label>
              <div class="col-sm-9">
                <input type="text" class="form-control" id="inputLastName" name="lastname" data-validation="alphanumeric" data-validation-allowing=" " placeholder="Last Name">
              </div>
            </div>
            <div class="form-group">
              <label for="inputZip" class="col-sm-3 control-label">Zip Code</label>
              <div class="col-sm-9">
                <input type="text" class="form-control" id="inputZip" name="zip" data-validation="number" data-validation="length" data-validation-length="5-10" placeholder="Zip Code">
              </div>
            </div>
            <div class="form-group">
              <label for="inputPhone" class="col-sm-3 control-label">Phone</label>
              <div class="col-sm-9">
                <input type="text" class="form-control" id="inputPhone" name="phone" data-validation="number" data-validation="length" data-validation-length="9-20" placeholder="Phone">
              </div>
            </div>
            <div class="form-group">
              <label for="inputBirthday" class="col-sm-3 control-label">Date of Birth</label>
              <div class="col-sm-9">
                <!-- Month dropdown -->
                <select name="month" class="form-control month" name="birthday_day" data-validation="required">
                    <option value="01">January</option>
                    <option value="02">February</option>
                    <option value="03">March</option>
                    <option value="04">April</option>
                    <option value="05">May</option>
                    <option value="06">June</option>
                    <option value="07">July</option>
                    <option value="08">August</option>
                    <option value="09">September</option>
                    <option value="10">October</option>
                    <option value="11">November</option>
                    <option value="12">December</option>
                </select>
                <!-- Day dropdown -->
                <select name="day" class="form-control day" name="birthday_month" data-validation="required">
                  <script type="text/javascript">
                    for(var i = 1; i < 32; i++){
                    //for (var i = year; i >= 1990; i--) {
                      if (i < 10 ) {
                        document.write('<option value="'+i+'">0'+i+'</option>');
                      } else {
                        document.write('<option value="'+i+'">'+i+'</option>');
                      }
                    }
                  </script>
                </select>
                <select name="year" class="form-control year" name="birthday_year" data-validation="required">
                  <script type="text/javascript">
                    var currentDate = new Date();
                    var year = currentDate.getFullYear();
                    for(var i = 1920; i < year+1; i++){
                    //for (var i = year; i >= 1990; i--) {
                      document.write('<option value="'+i+'">'+i+'</option>');
                    }
                  </script>
                </select>
                </div>
            </div>
            <div class="form-group">
              <label class="col-sm-3 control-label" for="inputEmail">Email</label>
              <div class="col-sm-9">
                  <input id="inputEmail" class="form-control" name="email" type="email" data-validation="email" placeholder="Email"></input>
              </div>
            </div>
            <div class="form-group">
              <div class="col-sm-3 col-image">
                <img alt="We guarantee our rate" src="assets/img/100-guarantee.png"/>
              </div>
              <div class="col-sm-9">
                <div class="checkbox">
                  <label>
                    <input type="checkbox" name="non-owner" value="true">I need a non-owner policy
                  </label>
                </div>
                <button type="submit" class="btn btn-lg btn-get-free-quote">Get A Free Quote</button>
              </div>
            </div>
          </form>
        </div><!-- end .sendEmail -->
        </div>
        </div>
      </div>
    </div> <!-- end jumbotron -->
    <main class="main">
      <div class="container">
        <div class="row">
          <div class="col-md-7">
            <div class="yelp-promo">
              <img class="logo-yelp" alt="Yelp" src="assets/img/yelp-logo.png"/>
              <p>We have a <span class="text-muted">5 star</span> rating on <span class="text-muted">Yelp.</span></p>
            </div>

            <div class="image-responsive">
              <div class="image-inner">
                <img class="logo-yelp" alt="Yelp widget" src="assets/img/yelp-widget.png"/>
              </div>
            </div>

          </div>
          <div class="col-md-5">
            <div class="sidebar">
              <h3>SR-22s Are Also Associated With the Following:</h3>
              <ul>
                <li>DUI or DWI or any serious moving violation like Reckless Driving</li>
                <li>At-fault accidents while driving without insurance</li>
                <li>Repeat traffic offenses or getting too many tickets in a short time period</li>
                <li>License suspension or revoked license</li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </main>
    <footer class="footer">
      <div class="container">
        <p class="copiright">2003-2016. MIS Insurance Services, LLC. All rights reserved.</p>
        <div class="pull-right">
        <!--
          <img alt="Yelp 5 - star reviews" src="assets/img/yelp.png"/>
        -->
          <div id="yelp-biz-badge-rrc-cDQH9zJvxdVRwan3NiJkBQ"><a href="http://yelp.com/biz/mis-insurance-services-los-angeles" target="_blank">Check out MIS Insurance Services on Yelp</a></div><script>(function(d, t) {var g = d.createElement(t);var s = d.getElementsByTagName(t)[0];g.id = "yelp-biz-badge-script-rrc-cDQH9zJvxdVRwan3NiJkBQ";g.src = "//yelp.com/biz_badge_js/en_US/rrc/cDQH9zJvxdVRwan3NiJkBQ.js";s.parentNode.insertBefore(g, s);}(document, 'script'));</script>
          <img alt="Show Your Card & Save" src="assets/img/AAA-r.png"/>
        </div>
      </div>
    </footer>
    <!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="//cdnjs.cloudflare.com/ajax/libs/jquery-form-validator/2.2.43/jquery.form-validator.min.js"></script>
    <script src="assets/js/bootstrap.min.js"></script>

<script>
  $.validate({
    modules : 'security'
  });
</script>
  </body>
</html>
