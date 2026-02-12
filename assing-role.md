export MICROSERVICE_SP_OBJECT_ID=dfa4b016-210a-4ae6-8ffe-8ad0b25d6e4b
export APIM_PRINCIPAL_ID=69f15b5a-00dc-441e-a659-2d140412cfdf
export ROLE_ID=0cde922f-b217-42da-896e-a55fcc0b5025

az rest \
  --method POST \
  --uri "https://graph.microsoft.com/v1.0/servicePrincipals/${MICROSERVICE_SP_OBJECT_ID}/appRoleAssignedTo" \
  --body "{
    \"principalId\": \"${APIM_PRINCIPAL_ID}\",
    \"resourceId\": \"${MICROSERVICE_SP_OBJECT_ID}\",
    \"appRoleId\": \"${ROLE_ID}\"
  }"

  az rest \
  --method GET \
  --uri "https://graph.microsoft.com/v1.0/servicePrincipals/${MICROSERVICE_SP_OBJECT_ID}/appRoleAssignedTo"




(base) akash@MacBookPro aks-baseline-main % export MICROSERVICE_SP_OBJECT_ID=0c478ef1-36f8-4ee0-9ddf-f318646550dc
(base) akash@MacBookPro aks-baseline-main %   az rest \                                                        
  --method GET \
  --uri "https://graph.microsoft.com/v1.0/servicePrincipals/${MICROSERVICE_SP_OBJECT_ID}/appRoleAssignedTo"

{
  "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#appRoleAssignments",
  "value": [
    {
      "appRoleId": "755f2841-2236-0dd3-9481-61abf02166a2",
      "createdDateTime": "2026-02-12T06:03:41.8745433Z",
      "deletedDateTime": null,
      "id": "qhHJINnvIEWobjNaFl2zycARsXKbZNRDho0Z7woG3ps",
      "principalDisplayName": "aks-poc-apim",
      "principalId": "20c911aa-efd9-4520-a86e-335a165db3c9",
      "principalType": "ServicePrincipal",
      "resourceDisplayName": "test-app-reg",
      "resourceId": "0c478ef1-36f8-4ee0-9ddf-f318646550dc"
    }
  ]
}
