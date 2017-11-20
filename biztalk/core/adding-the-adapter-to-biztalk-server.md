---
redirect_url: /biztalk/core/adding-biztalk-adapter-for-jd-edwards-oneworld/
redirect_document_id: True
ROBOTS: NOINDEX
ms.openlocfilehash: 0491ac0f26b19a96d11cf633263010026961c58b
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="adding-the-adapter-to-biztalk-server"></a><span data-ttu-id="aa281-101">Agregar el adaptador a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="aa281-101">Adding the Adapter to BizTalk Server</span></span>
<span data-ttu-id="aa281-102">El adaptador de BizTalk para JD Edwards OneWorld contiene las carpetas Controlador de recepción y Controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="aa281-102">Microsoft BizTalk Adapter for JD Edwards OneWorld contains both the Receive Handler and Send Handler folders.</span></span> <span data-ttu-id="aa281-103">La carpeta Controlador de envío contiene BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="aa281-103">The Send Handler folder contains BizTalkServerApplication.</span></span> <span data-ttu-id="aa281-104">El adaptador de BizTalk para JD Edwards OneWorld se puede crear; se ejecuta en curso con BizTalk Server y no se ejecuta en un proceso de host aislado.</span><span class="sxs-lookup"><span data-stu-id="aa281-104">BizTalk Adapter for JD Edwards OneWorld is creatable; it runs in-process with BizTalk Server and does not run in an isolated host process.</span></span>  
  
 <span data-ttu-id="aa281-105">Use el procedimiento siguiente para agregar el adaptador a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="aa281-105">Use the following procedure to add the adapter to BizTalk Server.</span></span>  
  
### <a name="to-add-biztalk-adapter-for-jd-edwards-oneworld"></a><span data-ttu-id="aa281-106">Procedimiento para agregar el adaptador de BizTalk para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="aa281-106">To add BizTalk Adapter for JD Edwards OneWorld</span></span>  
  
1.  <span data-ttu-id="aa281-107">En el **iniciar** menú, elija **archivos de programa**, seleccione [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server** para iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="aa281-107">On the **Start** menu, point to **Program Files**, point to [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration** to start the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span>  
  
2.  <span data-ttu-id="aa281-108">Expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y, a continuación, expanda **configuración de plataforma**.</span><span class="sxs-lookup"><span data-stu-id="aa281-108">Expand **BizTalk Server Administration**, expand **BizTalk Group**, and then expand **Platform Settings**.</span></span>  
  
3.  <span data-ttu-id="aa281-109">Haga clic en **adaptadores**, seleccione **New**y haga clic en **adaptador**.</span><span class="sxs-lookup"><span data-stu-id="aa281-109">Right-click **Adapters**, point to **New**, and click **Adapter**.</span></span>  
  
4.  <span data-ttu-id="aa281-110">En el **propiedades del adaptador** cuadro de diálogo, escriba un nombre para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="aa281-110">In the **Adapter Properties** dialog box, type a name for the adapter.</span></span> <span data-ttu-id="aa281-111">Por ejemplo, JDEdwards.</span><span class="sxs-lookup"><span data-stu-id="aa281-111">For example, JDEdwards.</span></span>  
  
5.  <span data-ttu-id="aa281-112">Seleccione **JDEOneWorld** desde el **adaptador** lista y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aa281-112">Select **JDEOneWorld** from the **Adapter** list, and then click **OK**.</span></span>  
  
## <a name="verifying-the-adapter"></a><span data-ttu-id="aa281-113">Verificación del adaptador</span><span class="sxs-lookup"><span data-stu-id="aa281-113">Verifying the Adapter</span></span>  
 <span data-ttu-id="aa281-114">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, puede comprobar que el adaptador funciona correctamente examinando el **sistema lógico** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa281-114">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, you can verify that the adapter is functioning correctly by looking at the **Logical System** window.</span></span> <span data-ttu-id="aa281-115">En la instalación inicial, esta ventana está vacía, porque todavía no se ha establecido ninguna conexión con el sistema de servidor ni se ha creado ningún sistema lógico.</span><span class="sxs-lookup"><span data-stu-id="aa281-115">On initial installation, this window is empty because you have not yet established a connection to the server system, nor have you created any logical systems.</span></span>  
  
#### <a name="to-verify-that-the-adapter-is-running-correctly"></a><span data-ttu-id="aa281-116">Procedimiento para verificar que el adaptador funciona correctamente</span><span class="sxs-lookup"><span data-stu-id="aa281-116">To verify that the adapter is running correctly</span></span>  
  
1.  <span data-ttu-id="aa281-117">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda **grupo de BizTalk**, expanda **configuración de plataforma**, expanda **adaptadores**y, a continuación, seleccione  **JDEOneWorld**.</span><span class="sxs-lookup"><span data-stu-id="aa281-117">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **BizTalk Group**, expand **Platform Settings**, expand **Adapters**, and then select **JDEOneWorld**.</span></span>  
  
2.  <span data-ttu-id="aa281-118">En el panel de detalles, haga clic en **BizTalkServerApplication**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="aa281-118">In the details pane, right-click **BizTalkServerApplication**, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="aa281-119">Haga clic en la pestaña **Propiedades** .</span><span class="sxs-lookup"><span data-stu-id="aa281-119">Click the **Properties** tab.</span></span>  
  
4.  <span data-ttu-id="aa281-120">Establezca los parámetros de la conexión SQL.</span><span class="sxs-lookup"><span data-stu-id="aa281-120">Set the SQL Connection parameters.</span></span>  
  
    -   <span data-ttu-id="aa281-121">**Definir parámetros de la base de datos SQL -** el nombre de SQL Server y la base de datos son los que se establecen durante la instalación.</span><span class="sxs-lookup"><span data-stu-id="aa281-121">**Define SQL Database Parameters -** The SQL Server Name and Database are those you set at installation.</span></span> <span data-ttu-id="aa281-122">Esta es el área de texto en la que se puede redefinir el servidor y la base de datos del adaptador.</span><span class="sxs-lookup"><span data-stu-id="aa281-122">This is the text area that you can redefine the server and database for this adapter.</span></span>  
  
5.  <span data-ttu-id="aa281-123">Haga clic en **cerrar** para salir del **sistema lógico** ventana.</span><span class="sxs-lookup"><span data-stu-id="aa281-123">Click **Close** to exit the **Logical System** window.</span></span>  
  
     <span data-ttu-id="aa281-124">El siguiente paso es agregar un sistema lógico mediante [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="aa281-124">Your next step is to add a logical system using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa281-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="aa281-125">See Also</span></span>  
 <span data-ttu-id="aa281-126">[Planeamiento y arquitectura](../core/planning-and-architecture17.md) </span><span class="sxs-lookup"><span data-stu-id="aa281-126">[Planning and Architecture](../core/planning-and-architecture17.md) </span></span>  
 <span data-ttu-id="aa281-127">[Seguridad en el adaptador de BizTalk para JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="aa281-127">[Security in BizTalk Adapter for JD Edwards OneWorld](../core/security-in-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="aa281-128">Agregación del adaptador de BizTalk para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="aa281-128">Adding BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)