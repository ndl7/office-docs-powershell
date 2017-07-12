---
applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015
schema: 2.0.0
---

# New-CsSimpleUrlConfiguration

## SYNOPSIS
**Below Content Applies To:** Lync Server 2010

Creates a new simple URL configuration collection.
Simple URLs make it easier for users to join meetings and conferences, as well as making it easier for Administrators to log on to the Microsoft Lync Server 2010 Control Panel.

**Below Content Applies To:** Lync Server 2013

Creates a new simple URL configuration collection.
Simple URLs make it easier for users to join meetings and conferences.
They also make it easier for Administrators to sign in to the Lync Server Control Panel.
This cmdlet was introduced in Lync Server 2010.

**Below Content Applies To:** Skype for Business Server 2015

Creates a new simple URL configuration collection.
Simple URLs make it easier for users to join meetings and conferences.
They also make it easier for Administrators to sign in to the Skype for Business Server Control Panel.
This cmdlet was introduced in Lync Server 2010.



## SYNTAX

```
New-CsSimpleUrlConfiguration [-Identity] <XdsIdentity> [-SimpleUrl <PSListModifier>] [-InMemory] [-Force]
 [-Tenant <Guid>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Below Content Applies To:** Lync Server 2010

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else.
The simple URLs introduced in Lync Server 2010 help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are an improvement over the URLs used in Office Communications Server.
However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself.
In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your Front End Server certificates; and so on.

Lync Server enables you to create three different simple URLs:

Meet - Used for meetings.
You must have at least one Meet URL for each of your SIP domains.

Admin - Used to point administrators towards the Lync Server 2010 Control Panel.

Dialin - Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections.
When you install Lync Server, a global collection is created for you; you can also create custom collections at the site scope.
This gives you the ability to use different simple URLs at each of your sites.

Simple URL configuration collections are created by using the New-CsSimpleUrlConfiguration cmdlet; you can then use additional cmdlets (such as New-CsSimpleUrl and Set-CsSimpleUrlConfiguration) to populate these collections with simple URLs.
After updating a simple URL collection you must then run the Enable-CsComputer cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsSimpleUrlConfiguration cmdlet locally: RTCUniversalServerAdmins.
To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object  {$_.Cmdlets -match "New-CsSimpleUrlConfiguration"}

**Below Content Applies To:** Lync Server 2013

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else.
The simple URLs introduced in Lync Server 2010 help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are an improvement over the URLs used in Office Communications Server.
However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself.
In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your Front End Server certificates; and so on.

Lync Server enables you to create three different simple URLs:

Meet - Used for meetings.
You must have at least one Meet URL for each of your SIP domains.

Admin - Used to point administrators toward the Lync Server Control Panel.

Dialin - Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections.
When you install Lync Server, a global collection is created for you; you can also create custom collections at the site scope.
This gives you the ability to use different simple URLs at each of your sites.

Simple URL configuration collections are created by using the New-CsSimpleUrlConfiguration cmdlet; you can then use additional cmdlets (such as New-CsSimpleUrl and Set-CsSimpleUrlConfiguration) to populate these collections with simple URLs.
After updating a simple URL collection you must then run the Enable-CsComputer cmdlet.

Who can run this cmdlet: By default, members of the following groups are authorized to run the New-CsSimpleUrlConfiguration cmdlet locally: RTCUniversalServerAdmins.
To return a list of all the role-based access control (RBAC) roles this cmdlet has been assigned to (including any custom RBAC roles you have created yourself), run the following command from the Windows PowerShell prompt:

Get-CsAdminRole | Where-Object {$_.Cmdlets -match "New-CsSimpleUrlConfiguration"}

**Below Content Applies To:** Skype for Business Server 2015

In Microsoft Office Communications Server 2007 R2, meetings had URLs similar to this:

https://imdf.litwareinc.com/Join?uri=sip%3Akenmyer%40litwareinc.com%3Bgruu%3Bopaque%3Dapp%3Aconf%3Afocus%3Aid%3A125f95a0b0184dcea706f1a0191202a8&key=EcznhLh5K5t

However, such URLs are not especially intuitive, and not easy to convey to someone else.
The simple URLs introduced in Lync Server 2010 help overcome those problems by providing users with URLs that look more like this:

https://meet.litwareinc.com/kenmyer/071200

Simple URLs are an improvement over the URLs used in Office Communications Server.
However, simple URLs are not automatically created for you; instead, you must configure the URLs yourself.
In addition, you must also do such things as create Domain Name System (DNS) records for each URL; configure reverse proxy rules for external access; add the simple URLs to the your Front End Server certificates; and so on.

Skype for Business Server 2015 enables you to create three different simple URLs:

Meet - Used for meetings.
You must have at least one Meet URL for each of your SIP domains.

Admin - Used to point administrators toward the Skype for Business Server Control Panel.

Dialin - Used for the dial-in conferencing webpage.

Simple URLs are stored in simple URL configuration collections.
When you install Skype for Business Server 2015, a global collection is created for you; you can also create custom collections at the site scope.
This gives you the ability to use different simple URLs at each of your sites.

Simple URL configuration collections are created by using the New-CsSimpleUrlConfiguration cmdlet; you can then use additional cmdlets (such as the New-CsSimpleUrl cmdlet and the Set-CsSimpleUrlConfiguration cmdlet) to populate these collections with simple URLs.
After updating a simple URL collection you must then run the Enable-CsComputer cmdlet.



## EXAMPLES

### -------------------------- Example 1 ------------------------ (Lync Server 2010)
```
New-CsSimpleUrlConfiguration -Identity "site:Redmond"
```

The command shown in Example 1 creates a new simple URL collection for the Redmond site.
Because no parameters other than Identity are included with this command, the new collection will not contain any simple URLs.
This command will fail if the Redmond site already hosts a simple URL collection.

### -------------------------- EXAMPLE 1 -------------------------- (Lync Server 2013)
```

```

The command shown in Example 1 creates a new simple URL collection for the Redmond site.
Because no parameters other than Identity are included with this command, the new collection will not contain any simple URLs.
This command will fail if the Redmond site already hosts a simple URL collection.

New-CsSimpleUrlConfiguration -Identity "site:Redmond"

### -------------------------- EXAMPLE 1 -------------------------- (Skype for Business Server 2015)
```

```

The command shown in Example 1 creates a new simple URL collection for the Redmond site.
Because no parameters other than Identity are included with this command, the new collection will not contain any simple URLs.
This command will fail if the Redmond site already hosts a simple URL collection.

New-CsSimpleUrlConfiguration -Identity "site:Redmond"

### -------------------------- Example 2 ------------------------ (Lync Server 2010)
```
$urlEntry = New-CsSimpleUrlEntry -Url "https://dialin.fabrikam.com"
$simpleUrl = New-CsSimpleUrl -Component "dialin" -Domain "*" -SimpleUrl $urlEntry -ActiveUrl "https://dialin.fabrikam.com"

$urlEntry2 = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"
$simpleUrl2 = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrl $urlEntry2 

New-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl,$simpleUrl2}
```

The preceding example shows how you can create a new collection of simple URLs that includes two simple URLs (one for meeting management and one for dial-in conferencing).
To do this, the first command in the example uses New-CsSimpleUrlEntry to create a URL entry that points to https://dialin.litwareinc.com; this URL entry is stored in a variable named $urlEntry.
The second command then creates another URL entry, this one pointing to https://meet.fabrikam.com.

Next, the New-CsSimpleUrl cmdlet is used to create an in-memory-only instance of a simple URL.
In this example, the URL Component is set to dialin; the domain is set to an asterisk (*); the ActiveUrl is set to https://dialin.fabrikam.com; and the SimpleUrl property is set to $urlEntry.
(The variable $urlEntry represents the URL entry created in the first command.) A similar command is then used to create a simple URL for meet.fabrikam.com.

After the URLs have been created (and stored in the object references $simpleUrl and $simpleUrl2) the final command in the example creates a new simple URL collection for the Redmond site, adding the two new in-memory-only URLs to that collection.
The new URLs are added to the collection by using the New-CsSimpleUrlConfiguration cmdlet, the SimpleUrl parameter, and the parameter value @{Add=$simpleUrl, $simpleUrl2}.
That syntax causes the URLs stored in the object references $simpleUrl and $simpleUrl2 to be added to the SimpleUrl property.

### -------------------------- EXAMPLE 2 -------------------------- (Lync Server 2013)
```

```

Example 2 shows how you can create a new collection of simple URLs that includes two simple URLs (one for meeting management and one for dial-in conferencing).
To do this, the first command in the example uses New-CsSimpleUrlEntry to create a URL entry that points to https://dialin.litwareinc.com; this URL entry is stored in a variable named $urlEntry.
The second command then creates another URL entry, this one pointing to https://meet.fabrikam.com.

Next, the New-CsSimpleUrl cmdlet is used to create an in-memory-only instance of a simple URL.
In this example, the URL Component is set to dialin; the domain is set to an asterisk (*); the ActiveUrl is set to https://dialin.fabrikam.com; and the SimpleUrl property is set to $urlEntry.
(The variable $urlEntry represents the URL entry created in the first command.) A similar command is then used to create a simple URL for meet.fabrikam.com.

After the URLs have been created (and stored in the object references $simpleUrl and $simpleUrl2) the final command in the example creates a new simple URL collection for the Redmond site, adding the two new in-memory-only URLs to that collection.
The new URLs are added to the collection by using the New-CsSimpleUrlConfiguration cmdlet, the SimpleUrl parameter, and the parameter value @{Add=$simpleUrl, $simpleUrl2}.
That syntax causes the URLs stored in the object references $simpleUrl and $simpleUrl2 to be added to the SimpleUrl property.

$urlEntry = New-CsSimpleUrlEntry -Url "https://dialin.fabrikam.com"

$simpleUrl = New-CsSimpleUrl -Component "dialin" -Domain "*" -SimpleUrl $urlEntry -ActiveUrl "https://dialin.fabrikam.com"

$urlEntry2 = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"

$simpleUrl2 = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrl $urlEntry2

New-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl,$simpleUrl2}

### -------------------------- EXAMPLE 2 -------------------------- (Skype for Business Server 2015)
```

```

Example 2 shows how you can create a new collection of simple URLs that includes two simple URLs (one for meeting management and one for dial-in conferencing).
To do this, the first command in the example uses the New-CsSimpleUrlEntry cmdlet to create a URL entry that points to https://dialin.litwareinc.com; this URL entry is stored in a variable named $urlEntry.
The second command then creates another URL entry, this one pointing to https://meet.fabrikam.com.

Next, the New-CsSimpleUrl cmdlet is used to create an in-memory-only instance of a simple URL.
In this example, the URL Component is set to dialin; the domain is set to an asterisk (*); the ActiveUrl is set to https://dialin.fabrikam.com; and the SimpleUrl property is set to $urlEntry.
(The variable $urlEntry represents the URL entry created in the first command.) A similar command is then used to create a simple URL for meet.fabrikam.com.

After the URLs have been created (and stored in the object references $simpleUrl and $simpleUrl2) the final command in the example creates a new simple URL collection for the Redmond site, adding the two new in-memory-only URLs to that collection.
The new URLs are added to the collection by using the New-CsSimpleUrlConfiguration cmdlet, the SimpleUrl parameter, and the parameter value @{Add=$simpleUrl, $simpleUrl2}.
That syntax causes the URLs stored in the object references $simpleUrl and $simpleUrl2 to be added to the SimpleUrl property.

$urlEntry = New-CsSimpleUrlEntry -Url "https://dialin.fabrikam.com"

$simpleUrl = New-CsSimpleUrl -Component "dialin" -Domain "*" -SimpleUrlEntry $urlEntry -ActiveUrl "https://dialin.fabrikam.com"

$urlEntry2 = New-CsSimpleUrlEntry -Url "https://meet.fabrikam.com"

$simpleUrl2 = New-CsSimpleUrl -Component "meet" -Domain "fabrikam.com" -SimpleUrlEntry $urlEntry2

New-CsSimpleUrlConfiguration -Identity "site:Redmond" -SimpleUrl @{Add=$simpleUrl,$simpleUrl2}

## PARAMETERS

### -Identity
**Below Content Applies To:** Lync Server 2010, Lync Server 2013

Unique identifier for the new simple URL configuration collection.
Because new collections can only be created at the site scope, the Identity must be the prefix "site:" followed by the name of the site.
For example, this syntax creates a new collection for the Redmond site: -Identity "site:Redmond".



**Below Content Applies To:** Skype for Business Server 2015

Unique identifier for the new simple URL configuration collection.
Because new collections can only be created at the site scope, the Identity must be the prefix "site:" followed by the name of the site.
For example, this syntax creates a new collection for the Redmond site:

-Identity "site:Redmond"



```yaml
Type: XdsIdentity
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SimpleUrl
**Below Content Applies To:** Lync Server 2010, Lync Server 2013

Simple URLs that have been configured for this collection.
These URLs must be created by using the New-SimpleUrl and New-SimpleUrlEntry cmdlets.



**Below Content Applies To:** Skype for Business Server 2015

Simple URLs that have been configured for this collection.
These URLs must be created by using the New-SimpleUrl cmdlet and the New-SimpleUrlEntry cmdlet.



```yaml
Type: PSListModifier
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InMemory
**Below Content Applies To:** Lync Server 2010, Lync Server 2013

Creates an object reference without actually committing the object as a permanent change.
If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet's matching Set- cmdlet.



**Below Content Applies To:** Skype for Business Server 2015

Creates an object reference without actually committing the object as a permanent change.
If you assign the output of this cmdlet called with this parameter to a variable, you can make changes to the properties of the object reference and then commit those changes by calling this cmdlet's matching Set-\<cmdlet\>.



```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Suppresses the display of any non-fatal error message that might occur when running the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tenant
**Below Content Applies To:** Lync Server 2010

This parameter is not used with the on-premises version of Lync Server.



**Below Content Applies To:** Lync Server 2013

Globally unique identifier (GUID) of the Office 365 tenant account for which the new Simple URL configuration settings are being created.
For example:

-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"

You can return the tenant ID for each of your tenants by running this command:

Get-CsTenant | Select-Object DisplayName, TenantID



**Below Content Applies To:** Skype for Business Server 2015

Globally unique identifier (GUID) of the Skype for Business Online tenant account for which the new Simple URL configuration settings are being created.
For example:

-Tenant "38aad667-af54-4397-aaa7-e94c79ec2308"

You can return the tenant ID for each of your tenants by running this command:

Get-CsTenant | Select-Object DisplayName, TenantID



```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Describes what would happen if you executed the command without actually executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before executing the command.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf
Applicable: Lync Server 2010, Lync Server 2013, Skype for Business Server 2015

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
None.

## OUTPUTS

###  
New-CsSimpleUrlConfiguration creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SimpleUrl.SimpleUrlConfiguration object.

###  
The New-CsSimpleUrlConfiguration cmdlet creates new instances of the Microsoft.Rtc.Management.WritableConfig.Settings.SimpleUrl.SimpleUrlConfiguration object.

## NOTES

## RELATED LINKS

[Online Version](http://technet.microsoft.com/EN-US/library/3140f15a-e448-42fe-b494-bf9caba32b35(OCS.14).aspx)

[Get-CsSimpleUrlConfiguration]()

[New-CsSimpleUrl]()

[New-CsSimpleUrlEntry]()

[Remove-CsSimpleUrlConfiguration]()

[Set-CsSimpleUrlConfiguration]()

[Online Version](http://technet.microsoft.com/EN-US/library/3140f15a-e448-42fe-b494-bf9caba32b35(OCS.15).aspx)

[Online Version](http://technet.microsoft.com/EN-US/library/3140f15a-e448-42fe-b494-bf9caba32b35(OCS.16).aspx)
