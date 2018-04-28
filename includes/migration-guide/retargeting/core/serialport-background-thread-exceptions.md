### <a name="serialport-background-thread-exceptions"></a><span data-ttu-id="81003-101">Exceptions de thread d’arrière-plan SerialPort</span><span class="sxs-lookup"><span data-stu-id="81003-101">SerialPort background thread exceptions</span></span>

|   |   |
|---|---|
|<span data-ttu-id="81003-102">Détails</span><span class="sxs-lookup"><span data-stu-id="81003-102">Details</span></span>|<span data-ttu-id="81003-103">Les threads d’arrière-plan créés avec des flux <xref:System.IO.Ports.SerialPort> ne terminent plus le processus quand des exceptions de système d’exploitation sont levées. Dans les applications qui ciblent .NET Framework 4.7 et les versions antérieures, un processus est terminé quand une exception de système d’exploitation est levée sur un thread d’arrière-plan créé avec un flux <xref:System.IO.Ports.SerialPort>. Dans les applications que ciblent .NET Framework 4.7.1 ou une version ultérieure, les threads d’arrière-plan attendent la fin des événements de système d’exploitation liés au port série actif et peuvent planter dans certains cas, comme la suppression soudaine du port série.</span><span class="sxs-lookup"><span data-stu-id="81003-103">Background threads created with <xref:System.IO.Ports.SerialPort> streams no longer terminate the process when OS exceptions are thrown.In applications that target the .NET Framework 4.7 and earlier versions, a process is terminated when an operating system exception is thrown on a background thread created with a <xref:System.IO.Ports.SerialPort> stream.In applications that target the .NET Framework 4.7.1 or a later version, background threads wait for OS events related to the active serial port and could crash in some cases, such as sudden removal of the serial port.</span></span>|
|<span data-ttu-id="81003-104">Suggestion</span><span class="sxs-lookup"><span data-stu-id="81003-104">Suggestion</span></span>|<span data-ttu-id="81003-105">Pour les applications qui ciblent .NET Framework 4.7.1, vous pouvez refuser la gestion des exceptions en ajoutant le code suivant à la section <code>&lt;runtime&gt;</code> de votre fichier <code>app.config</code> :</span><span class="sxs-lookup"><span data-stu-id="81003-105">For apps that target the .NET Framework 4.7.1, you can opt out of the exception handling if it is not desirable by adding the following to the <code>&lt;runtime&gt;</code> section of your <code>app.config</code> file:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre><span data-ttu-id="81003-106">Pour les applications qui ciblent des versions antérieures du .NET Framework mais qui s’exécutent sur .NET Framework 4.7.1 ou une version ultérieure, vous pouvez accepter la prise en charge de la gestion des exceptions en ajoutant le code suivant à la section <code>&lt;runtime&gt;</code> de votre fichier <code>app.config</code> :</span><span class="sxs-lookup"><span data-stu-id="81003-106">For apps that target earlier versions of the .NET Framework but run on the .NET Framework 4.7.1 or later, you can opt in to the exception handling by adding the following to the <code>&lt;runtime&gt;</code> section of your <code>app.config</code> file:</span></span><pre><code class="language-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.IO.Ports.DoNotCatchSerialStreamThreadExceptions=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="81003-107">Portée</span><span class="sxs-lookup"><span data-stu-id="81003-107">Scope</span></span>|<span data-ttu-id="81003-108">Mineur</span><span class="sxs-lookup"><span data-stu-id="81003-108">Minor</span></span>|
|<span data-ttu-id="81003-109">Version</span><span class="sxs-lookup"><span data-stu-id="81003-109">Version</span></span>|<span data-ttu-id="81003-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="81003-110">4.7.1</span></span>|
|<span data-ttu-id="81003-111">Type</span><span class="sxs-lookup"><span data-stu-id="81003-111">Type</span></span>|<span data-ttu-id="81003-112">Reciblage</span><span class="sxs-lookup"><span data-stu-id="81003-112">Retargeting</span></span>|
|<span data-ttu-id="81003-113">API affectées</span><span class="sxs-lookup"><span data-stu-id="81003-113">Affected APIs</span></span>|<ul><li><xref:System.IO.Ports.SerialPort?displayProperty=nameWithType></li></ul>|
