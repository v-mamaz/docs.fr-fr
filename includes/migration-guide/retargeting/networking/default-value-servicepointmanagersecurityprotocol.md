### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a><span data-ttu-id="fc75e-101">La valeur par défaut de ServicePointManager.SecurityProtocol est SecurityProtocolType.System.Default</span><span class="sxs-lookup"><span data-stu-id="fc75e-101">Default value of ServicePointManager.SecurityProtocol is SecurityProtocolType.System.Default</span></span>

|   |   |
|---|---|
|<span data-ttu-id="fc75e-102">Détails</span><span class="sxs-lookup"><span data-stu-id="fc75e-102">Details</span></span>|<span data-ttu-id="fc75e-103">À partir des applications qui ciblent .NET Framework 4.7, la valeur par défaut de la propriété <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> est <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fc75e-103">Starting with apps that target the .NET Framework 4.7, the default value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property is <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fc75e-104">Ce changement permet aux API de réseau .NET Framework basées sur SslStream (comme FTP, HTTPS et SMTP) d’hériter des protocoles de sécurité par défaut du système d’exploitation au lieu d’utiliser des valeurs codées en dur définies par le .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc75e-104">This change allows .NET Framework networking APIs based on SslStream (such as FTP, HTTPS, and SMTP) to inherit the default security protocols from the operating system instead of using hard-coded values defined by the .NET Framework.</span></span> <span data-ttu-id="fc75e-105">La valeur par défaut varie en fonction du système d’exploitation et des configurations personnalisées effectuées par l’administrateur système.</span><span class="sxs-lookup"><span data-stu-id="fc75e-105">The default varies by operating system and any custom configuration performed by the system administrator.</span></span> <span data-ttu-id="fc75e-106">Pour plus d’informations sur le protocole SChannel par défaut dans chaque version du système d’exploitation Windows, consultez [Protocoles dans TLS/SSL (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159.aspx). Pour les applications qui ciblent une version antérieure du .NET Framework, la valeur par défaut de la propriété <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> dépend de la version du .NET Framework ciblée.</span><span class="sxs-lookup"><span data-stu-id="fc75e-106">For information on the default SChannel protocol in each version of the Windows operating system, see [Protocols in TLS/SSL (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159.aspx).For applications that target an earlier version of the .NET Framework, the default value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property depends on the version of the .NET Framework targeted.</span></span> <span data-ttu-id="fc75e-107">Pour plus d’informations, consultez la [section Mise en réseau de la rubrique Modifications de reciblage pour la migration de .NET Framework 4.5.2 vers la version 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).</span><span class="sxs-lookup"><span data-stu-id="fc75e-107">See the [Networking section of Retargeting Changes for Migration from .NET Framework 4.5.2 to 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking) for more information.</span></span>|
|<span data-ttu-id="fc75e-108">Suggestion</span><span class="sxs-lookup"><span data-stu-id="fc75e-108">Suggestion</span></span>|<span data-ttu-id="fc75e-109">Ce changement affecte les applications qui ciblent .NET Framework 4.7 ou les versions ultérieures. Si vous préférez utiliser un protocole défini au lieu de vous appuyer sur la valeur par défaut du système, vous pouvez définir explicitement la valeur de la propriété <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>. Si ce changement n’est pas souhaitable, vous pouvez le refuser en ajoutant un paramètre de configuration à la section [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) de votre fichier de configuration d’application.</span><span class="sxs-lookup"><span data-stu-id="fc75e-109">This change affects applications that target the .NET Framework 4.7 or later versions.If you prefer to use a defined protocol rather than relying on the system default, you can explicitly set the value of the <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> property.If this change is undesirable, you can opt out of it by adding a configuration setting to the [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your application configuration file.</span></span> <span data-ttu-id="fc75e-110">L’exemple suivant montre la section <code>&lt;runtime&gt;</code> et l’option d’annulation <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> :</span><span class="sxs-lookup"><span data-stu-id="fc75e-110">The following example shows both the <code>&lt;runtime&gt;</code> section and the <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code> opt-out switch:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="fc75e-111">Portée</span><span class="sxs-lookup"><span data-stu-id="fc75e-111">Scope</span></span>|<span data-ttu-id="fc75e-112">Mineur</span><span class="sxs-lookup"><span data-stu-id="fc75e-112">Minor</span></span>|
|<span data-ttu-id="fc75e-113">Version</span><span class="sxs-lookup"><span data-stu-id="fc75e-113">Version</span></span>|<span data-ttu-id="fc75e-114">4.7</span><span class="sxs-lookup"><span data-stu-id="fc75e-114">4.7</span></span>|
|<span data-ttu-id="fc75e-115">Type</span><span class="sxs-lookup"><span data-stu-id="fc75e-115">Type</span></span>|<span data-ttu-id="fc75e-116">Reciblage</span><span class="sxs-lookup"><span data-stu-id="fc75e-116">Retargeting</span></span>|
|<span data-ttu-id="fc75e-117">API affectées</span><span class="sxs-lookup"><span data-stu-id="fc75e-117">Affected APIs</span></span>|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
