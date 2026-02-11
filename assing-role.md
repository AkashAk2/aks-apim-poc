az rest \
  --method POST \
  --uri "https://graph.microsoft.com/v1.0/servicePrincipals/${MICROSERVICE_SP_OBJECT_ID}/appRoleAssignedTo" \
  --body "{
    \"principalId\": \"${APIM_PRINCIPAL_ID}\",
    \"resourceId\": \"${MICROSERVICE_SP_OBJECT_ID}\",
    \"appRoleId\": \"${ROLE_ID}\"
  }"