# SoapUI
Using soapui to test server endpoint


I'm using REST request. JSON format.

Request needs params, endpoint, body, header,etc....

test codes example
===================================================================================
import groovy.json.JsonSlurper
def response = messageExchange.responseContent
def request = messageExchange.requestContent
def jsonResponse = new JsonSlurper().parseText(response)

assert jsonResponse.balanceAmount != null  : "Balance is missing in response!"
def balance = jsonResponse.balanceAmount;
assert balance.toLong() > 0:"Wrong balance in response! Must be positive value!!!";
===================================================================================
