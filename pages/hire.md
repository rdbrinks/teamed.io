---
layout: plain
title: "Hire Me"
permalink: /hire.html
description:
  In order to hire you, we have to collect this basic
  information
keywords:
  - hire software developer
  - remote programmer hire
  - hire programmer
  - start working remotely
  - hire a programmer
---

Please, fill this form if you want to work with us.

<style type="text/css">
  .help {
    font-size: 0.8em;
    color: gray;
  }
</style>
<form name="hire" name="form" ng-submit="submit()">
  <p>
    <label>Your full name</label><br/>
    <input name="name" style="width:12em" maxlength="100" ng-model="name" required/>
  </p>
  <p>
    <label>Hourly rate, in US dollars</label><br/>
    <input name="name" type="number" style="width:3em" maxlength="10" ng-model="rate" required/><br/>
    <span class="help">Keep this article in mind:
    <a href="http://www.yegor256.com/2014/10/29/how-much-do-you-cost.html">How Much Do You Cost?</a></span>
  </p>
  <p>
    <label>Phone number</label><br/>
    <input name="phone" style="width:10em" maxlength="20" ng-model="phone" required/><br/>
    <span class="help">Our customers require us to collect this information
    from all our engineers, programmers, testers, DevOps, etc. We have
    to know who we're working with, in order to guarantee our clients
    a certain level of security of their sensitive information. We won't
    call you or mail you.</span>
  </p>
  <p>
    <label>Country</label><br/>
    <input name="country" style="width:9em" maxlength="50" ng-model="country" required/>
  </p>
  <p>
    <label>Postal address</label><br/>
    <input name="address" style="width:20em" maxlength="150" ng-model="address" required/>
  </p>
  <p>
    <label>Email</label><br/>
    <input name="email" type="email" style="width:11em" maxlength="100" ng-model="email" required/>
  </p>
  <p>
    <label><a href="https://github.com">GitHub</a> account name</label><br/>
    <input name="github" type="text" style="width:8em" maxlength="50" ng-model="github" required/><br/>
    <span class="help">As <a href="http://www.yegor256.com/2014/10/07/stop-chatting-start-coding.html">this article</a> explains,
    we use only GitHub tickets to communicate in a project, no
    emails, chats, meetings, or phone calls.</span>
  </p>
  <p>
    <label><a href="http://www.netbout.com">Netbout</a> account name</label><br/>
    <input name="netbout" style="width:8em" maxlength="50" ng-model="netbout" required/><br/>
    <span class="help">We use Netbout for out-of-project discussions,
    related to payments, disciplinary actions, rating, performance
    appraisals, etc. Netbout integrates our management and automated
    reporting tools. If you don't have a Netbout account, create it now,
    should take less than a minute. Don't forget to register your email
    there, to stay tuned on updates.</span>
  </p>
  <p>
    <label>How can we pay you?</label><br/>
    <input name="wallet" style="width:13em" maxlength="100" ng-model="wallet" required/><br/>
    <span class="help">There are two options at the moment:
    <a href="http://www.paypal.com">PayPal</a> or <a href="http://www.upwork.com">Upwork</a>.
    If you want us to pay through PayPal, just give the email of
    your PayPal account. If you want Upwork, give the contract number.</span>
  </p>
  <p>
    <button id='submit'>Submit</button><br/>
    <span class="help">Right after you click this button, we create a new
    conversation in Netbout. One of us will reply to you
    in 24 hours.</span>
  </p>
</form>

<script>
var app = angular.module('teamed', []);
app.config(
  [
    '$locationProvider',
    function($locationProvider) {
      $locationProvider.html5Mode(true);
    }
  ]
);
app.controller(
  'Main',
  [
    '$scope', '$location',
    function($scope, $location) {
      $scope.submit = function() {
        var text = 'name=' + $scope.name
          + '; rate=$' + $scope.rate + '/hr'
          + '; phone=' + $scope.phone
          + '; country=' + $scope.country
          + '; address=' + $scope.address
          + '; email=' + $scope.email
          + '; github=' + $scope.github
          + '; netbout=' + $scope.netbout
          + '; wallet=' + $scope.wallet;
        var url = 'http://www.netbout.com/start?post='
          + encodeURIComponent(text)
          + '&invite=yegor256&rename='
          + encodeURIComponent($scope.github);
        window.location = url;
      }
    }
  ]
);
</script>