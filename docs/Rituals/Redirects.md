# Redirects

## How to:

1. Go to our Postman Collection
2. Find the SFCC SCAPI - CDN ZONES
3. Send request to GET ACCESS TOKEN to update the variable
4. Use ```GET Zones Info``` to get all zones and find the id's of the ones required

Example of the staging zone: 
```json
{
"zoneId": "ca5ee5e55fccf2566461f33ceaf44f6c",
"name": "stg-bbkl-rituals-staging-com.cc-ecdn.net",
"status": "active"
}
```

5. Copy the zoneID and paste it in the variables of the collection
6.  Use ```GET MRT RULES``` to get all the current rules/rulesets of the selected zone, this contains the ```rulesetID``` and ```ruleID```
7. If updating a current rule with new TUs, run copy its ```rule.id``` and its ```ruleset.id``` and paste in in the variables. MAKE SURE THAT THEY ARE CORRECT, DOUBLE CHECK!
8. Go to ```Update MRT Rule``` and in the body add the following JSON:

```JSON
{ "expression": "(http.host eq \"www.rituals.com\") and (http.request.uri.path matches \"^/[a-z]{2,3}-[a-z]{2}/.*-(1116397|1113916|1113919|1113915|newTU|newTU).html$\")" }

```

*TIP:* You can copy the expression json from the rule you are updating and just paste it and modify it.
9. Send the request, and all should be good.


### Creating a new ruleset

1. Get MRT RUles -> copy ruleset id, add it to variables, and make sure rule id is empty in this case.
2. Update MRT Ruleset -> add a json of this format to the body

```json
    {
                    "expressions": ["(http.host eq \"www.rituals-staging.com\") and (http.request.uri.path matches \"^/[a-z]{2,3}-[a-z]{2}/.*-(1114962|1116080|1116240|1109802|1116082|1111804|1116081|1116431|1116432|1114338|1114956|1114334|1116433|1115507|1118089|1115545|1115462|1115467|1115468|1115471|1115503|1115463|1115464|1106403|15470|1115438|1115435|1116984|1116242|1116116|1115577|1115578|1116437|1116438|1115080|1114331|1114335|1116439|1115505|1115579|1115580|1118091|1118092|1118115|1115271|1115272|1115273|1115274|1115388|1114649|1115390|1115283|1115389|1115502|1115276|1116587|1115076|1116119|1115582|1115583|1115581|1116442|1116443|1114333|1116444|1116441|1115509|1118093|1115512|1116122|1116066|1116067|1117168|1109634|1109635|1109633|1116368|1117275|1116131|1116129|1116130|1117161|1117935|1116132|1118113|1116321|1115586|1115587|1115584|1115585|1118045|1116449|1116451|1114332|1116452|1115506|1118094|1117154|1117148|1117149|1117155|1117152|1117218|1117153|1117156|1117866|1115087|1113622|1116147|1116413|1116414|1114339|1118114|1118090|1118107|1118106|1115795|1115797|1115796|1115565|1115566|1115563|1115564|1116308|1115513|1115568|1115569|1115567|1118385|1118384|1118386|1115704|1115706|1115705|1115666|1115668|1115667|1118096|1115809|1115811|1115810).html$\")"],
                    "mrtHostname": "rituals-react-projec-staging.mobify-storefront.com"
                }
```
3. Send request, but double check before that it's the correct ruleset id.
4. All done. 

