## documentation

### Tutorials : 
1. Create an Azure AD B2C tenant
	https://docs.microsoft.com/en-us/azure/active-directory-b2c/tutorial-create-tenant
2. Register a web application
3. Create user flows and custom policies



### How to guides:
- UX customization

	Customize with HTML

	https://docs.microsoft.com/en-us/azure/active-directory-b2c/configure-user-input?pivots=b2c-custom-policy

- Custom attributes / Define custom attributes

- API connectors

	https://docs.microsoft.com/en-us/azure/active-directory-b2c/add-api-connector-token-enrichment?pivots=b2c-custom-policy




### Reference:  https://docs.microsoft.com/en-us/azure/active-directory-b2c/trustframeworkpolicy
Custom policy schema

	-- ## TrustFrameworkPolicy ##
		top-level element of a policy file.

-----------------------------------------------------------------------------------

	-- ## BuildingBlocks ##
		inside the TrustFrameworkPolicy element.

		<BuildingBlocks>
		    <ClaimsSchema>
		      ...
		    </ClaimsSchema>
		    <Predicates>
		    ...
		    </Predicates>
		    <PredicateValidations>
		    ...
		    </PredicateValidations>
		    <ClaimsTransformations>
		      ...
		    </ClaimsTransformations>
		    <ContentDefinitions>
		      ...
		    </ContentDefinitions>
		    <Localization>
		      ...
		    </Localization>
		    <DisplayControls>
		      ...
		    </DisplayControls>
		</BuildingBlocks>
 		
--------------------------------------------------------------------------------

	-- ## ClaimsProviders  ##
		interface to communicate with different types of parties via its technical profiles.

		<ClaimsProviders>
		  <ClaimsProvider>
		    <Domain>Domain name</Domain>
		    <DisplayName>Display name</DisplayName>
		    <TechnicalProfiles>
		      </TechnicalProfile>
		        ...
		      </TechnicalProfile>
		        ...
		    </TechnicalProfiles>
		  </ClaimsProvider>
		  ...
		</ClaimsProviders>

------------------------------------------------------------------------------

	-- ##  Technical Profiles  ##
	 A technical profile provides a framework with a built-in mechanism to communicate with different types of parties. Technical profiles are used to communicate with your Azure Active Directory B2C (Azure AD B2C) tenant to create a user or read a user profile. A technical profile can be self-asserted to enable interaction with the user. For example, a technical profile can collect the user's credential to sign in and then render the sign-up page or password reset page.

   ->>>>> https://docs.microsoft.com/en-us/azure/active-directory-b2c/technicalprofiles

----------------------------------------------------------------------------------

	-- ### UserJourneys  ##
	 User journeys specify explicit paths through which a policy allows a relying party application to obtain the desired claims for a user. The user is taken through these paths to retrieve the claims that are to be presented to the relying party. In other words, user journeys define the business logic of what an end user goes through as the Azure AD B2C Identity Experience Framework processes the request.

   ->>>>> https://docs.microsoft.com/en-us/azure/active-directory-b2c/userjourneys

	    <UserJourney Id="UserInfoJourney" DefaultCpimIssuerTechnicalProfileReferenceId="UserInfoIssuer">
		  <Authorization>
		    <AuthorizationTechnicalProfiles>
		      <AuthorizationTechnicalProfile ReferenceId="UserInfoAuthorization" />
		    </AuthorizationTechnicalProfiles>
		  </Authorization>
		  <OrchestrationSteps>
		    <OrchestrationStep Order="1" Type="ClaimsExchange">
		     ...

-------------------------------------------------------------------------------------

	-- ##  RelyingParty  ##
	  specifies the user journey to enforce for the current request to Azure Active Directory B2C (Azure AD B2C). It also specifies the list of claims that the relying party (RP) application needs as part of the issued token.

   ->>>>> https://docs.microsoft.com/en-us/azure/active-directory-b2c/relyingparty

## Tasks logs

1. custom UI (change style and logo..)
2. custom UI (add custom attribute, emit it in token)
3. collect useremail and if user is new take them to sign up and if the user is old take them to enter password.
4. get customerId from external api(function app) and put it into token.
5. password strength indicator

## 