---
title: Cómo implementar un adaptador personalizado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f17b336c-6232-4889-ab7e-92b83fab0f5f
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e36443b99f01688a38e66a4a302ab64bb220092f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250300"
---
# <a name="how-to-deploy-a-custom-adapter"></a><span data-ttu-id="8e91d-102">Cómo implementar un adaptador personalizado</span><span class="sxs-lookup"><span data-stu-id="8e91d-102">How to Deploy a Custom Adapter</span></span>
<span data-ttu-id="8e91d-103">Un proceso completo de instalación de adaptador se compone de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="8e91d-103">A complete adapter installation process consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="8e91d-104">Comprobar dependencias.</span><span class="sxs-lookup"><span data-stu-id="8e91d-104">Check dependencies.</span></span> <span data-ttu-id="8e91d-105">Por ejemplo, el instalador del adaptador de MSMQ comprueba la existencia del servicio local de MSMQ, ya que el tiempo de ejecución del adaptador depende de ello.</span><span class="sxs-lookup"><span data-stu-id="8e91d-105">For example, the MSMQ adapter installer checks for the existence of the local MSMQ service because the adapter runtime depends on it.</span></span>  
  
2.  <span data-ttu-id="8e91d-106">Configurar el sistema de archivos local.</span><span class="sxs-lookup"><span data-stu-id="8e91d-106">Set up the local file system.</span></span> <span data-ttu-id="8e91d-107">Incluye la creación de carpeta de instalación y la copia de archivos de compatibilidad y binarios.</span><span class="sxs-lookup"><span data-stu-id="8e91d-107">This includes creating installation folders and copying binary and support files.</span></span> <span data-ttu-id="8e91d-108">Asegúrese de que tiene acceso a las carpetas y que los permisos de acceso de archivo se han configurado adecuadamente.</span><span class="sxs-lookup"><span data-stu-id="8e91d-108">Ensure access to folders and file access permissions are configured properly.</span></span>  
  
3.  <span data-ttu-id="8e91d-109">Instalar ensamblados administrados en la caché de ensamblados global del sistema.</span><span class="sxs-lookup"><span data-stu-id="8e91d-109">Install managed assemblies into the system global assembly cache.</span></span>  
  
4.  <span data-ttu-id="8e91d-110">Crear claves del Registro para el adaptador.</span><span class="sxs-lookup"><span data-stu-id="8e91d-110">Create registry keys for the adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="8e91d-111">Para un adaptador de 32 bits, la consola de administración de BizTalk Server utiliza la rama HKEY_CLASSES_ROOT del Registro para obtener una configuración de adaptador personalizada.</span><span class="sxs-lookup"><span data-stu-id="8e91d-111">For a 32-bit adapter, the BizTalk Server Administration Console uses the HKEY_CLASSES_ROOT branch in the registry to obtain custom adapter configuration.</span></span>  <span data-ttu-id="8e91d-112">Si un adaptador de 32 bits se instala en un servidor de 64 bits, la consola de administración de BizTalk Server utilizará la rama HKEY_CLASSES_ROOT\Wow6432Node\ para los datos de configuración de adaptador.</span><span class="sxs-lookup"><span data-stu-id="8e91d-112">If a 32-bit adapter is installed on a 64-bit server, the BizTalk Serve Administration Console instead uses the HKEY_CLASSES_ROOT\Wow6432Node\ branch for adapter configuration data.</span></span>  
  
5.  <span data-ttu-id="8e91d-113">Agregar el adaptador a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8e91d-113">Add the adapter to BizTalk Server.</span></span> <span data-ttu-id="8e91d-114">Esto significa que las nuevas entradas de la base de datos de administración de BizTalk del adaptador y del esquema de propiedades se han utilizado para reflejar propiedades promovidas por el adaptador.</span><span class="sxs-lookup"><span data-stu-id="8e91d-114">This means new entries in the BizTalk Management database for the adapter as well as for the property schema used to reflect properties the adapter promotes.</span></span> <span data-ttu-id="8e91d-115">Este paso se realiza a veces manualmente con la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8e91d-115">This step is sometimes done manually using the BizTalk Server Administration console.</span></span>  
  
## <a name="exceptions"></a><span data-ttu-id="8e91d-116">Excepciones</span><span class="sxs-lookup"><span data-stu-id="8e91d-116">Exceptions</span></span>  
 <span data-ttu-id="8e91d-117">Es posible que el instalador de adaptador no tenga que comprobar las dependencias en las instalaciones parciales de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8e91d-117">The adapter installer may not need to check the dependencies in partial BizTalk Server installations.</span></span> <span data-ttu-id="8e91d-118">Por ejemplo, en una instalación solo de herramientas administrativas no es necesario comprobar las dependencias del tiempo de ejecución del adaptador, ya que el tiempo de ejecución del adaptador no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8e91d-118">For example, in an administration tools-only installation, the adapter installer does not need to check adapter runtime dependencies because the adapter runtime is not used.</span></span> <span data-ttu-id="8e91d-119">Lo mismo sucede en la instalación solo de tiempo de ejecución de BizTalk Server, en la que no es necesario que el instalador de adaptador compruebe las dependencias de tiempo de diseño de adaptador.</span><span class="sxs-lookup"><span data-stu-id="8e91d-119">The same is true in the BizTalk Server runtime-only installation, where the adapter installer does not need to check the adapter design-time dependencies.</span></span>  
  
 <span data-ttu-id="8e91d-120">En varios entornos de BizTalk Server, el último paso de la lista anterior (Agregar el adaptador a BizTalk Server) solo se realiza en la instalación de adaptador del primer servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="8e91d-120">In multiple BizTalk Server environments, the last step in the preceding list (Add the adapter to BizTalk Server) only happens in the adapter installation on the first BizTalk Server.</span></span> <span data-ttu-id="8e91d-121">Esto sucede porque todas las instancias del servicio de BizTalk Server comparten la misma base de datos de administración de BizTalk (con el nombre predeterminado BizTalkMgmtDB).</span><span class="sxs-lookup"><span data-stu-id="8e91d-121">This is because all BizTalk Server service instances share the same BizTalk Management database (with the default name, BizTalkMgmtDB).</span></span> <span data-ttu-id="8e91d-122">Si los adaptadores se han agregado a otros servidores de BizTalk Server del mismo grupo, los pasos adicionales producirán un error.</span><span class="sxs-lookup"><span data-stu-id="8e91d-122">If adapters are added to other BizTalk servers in the same group, the additional steps fail.</span></span>  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a><span data-ttu-id="8e91d-123">Instalar los ensamblados de adaptador en la caché de ensamblados global</span><span class="sxs-lookup"><span data-stu-id="8e91d-123">Install the Adapter Assemblies into the Global Assembly Cache</span></span>  
 <span data-ttu-id="8e91d-124">Para compatibilizar varios entornos de host de BizTalk Server con diferentes rutas de instalación de adaptador, los ensamblados de adaptador deben instalarse en la caché de ensamblados global del sistema.</span><span class="sxs-lookup"><span data-stu-id="8e91d-124">To support multiple BizTalk Server host environments with different adapter installation paths, the adapter assemblies must be installed into the system global assembly cache.</span></span>  
  
 <span data-ttu-id="8e91d-125">Durante la instalación y configuración de adaptador, se crea una nueva entrada de adaptador en la tabla adm_adapter de la base de datos de administración de BizTalk (con el nombre predeterminado BizTalkMgmtDB).</span><span class="sxs-lookup"><span data-stu-id="8e91d-125">During the adapter installation and configuration, a new adapter entry is created in the adm_adapter table of the BizTalk Management database (with the default name BizTalkMgmtDB).</span></span> <span data-ttu-id="8e91d-126">Esta entrada contiene toda la información de referencia utilizada por BizTalk Server durante el tiempo de ejecución y el tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="8e91d-126">This entry contains all reference information used by BizTalk Server for both run time and design time.</span></span>  
  
 <span data-ttu-id="8e91d-127">El **InBoundAssemblyPath** y **OutboundAssemblyPath** campos se usan en tiempo de ejecución de BizTalk Server para averiguar dónde se deben cargar los archivos binarios del adaptador.</span><span class="sxs-lookup"><span data-stu-id="8e91d-127">The **InBoundAssemblyPath** and **OutboundAssemblyPath** fields are used by the BizTalk Server runtime to find out where to load the adapter binaries.</span></span> <span data-ttu-id="8e91d-128">Puesto que solo hay una base de datos de administración de BizTalk para un grupo de BizTalk Server, todos los servidores de BizTalk Server del grupo deben compartir esta misma información.</span><span class="sxs-lookup"><span data-stu-id="8e91d-128">Because there is only one BizTalk Management database for a BizTalk Server group, all BizTalk servers in the group must share this same piece of information.</span></span> <span data-ttu-id="8e91d-129">Si desea instalar el adaptador en diferentes servidores de BizTalk Server dentro del grupo, debe utilizar la misma ruta de instalación en cada uno de los servidores.</span><span class="sxs-lookup"><span data-stu-id="8e91d-129">If you want to install the adapter on different BizTalk servers within the group, you must use the same installation path on each of those servers.</span></span> <span data-ttu-id="8e91d-130">Si la ruta de instalación local es diferente de la ruta almacenada en la base de datos de administración de BizTalk, BizTalk Server no puede cargar los binarios de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="8e91d-130">If the local installation path is different from the path stored in the BizTalk Management database, BizTalk Server cannot load the adapter binaries.</span></span>  
  
 <span data-ttu-id="8e91d-131">Firme siempre el ensamblado de adaptador con un nombre seguro y utilice Gacutil.exe para colocar el ensamblado de adaptador en la caché de ensamblados global del sistema durante la instalación del adaptador.</span><span class="sxs-lookup"><span data-stu-id="8e91d-131">Always sign the adapter's assembly with a strong name and use Gacutil.exe to put the adapter assembly into the system global assembly cache during the adapter installation.</span></span> <span data-ttu-id="8e91d-132">Asegúrese de que deje el **InBoundAssemblyPath** y **OutboundAssemblyPath** campos null ni estar vacíos.</span><span class="sxs-lookup"><span data-stu-id="8e91d-132">Make sure that you leave the **InBoundAssemblyPath** and **OutboundAssemblyPath** fields null, or empty.</span></span>  
  
## <a name="using-the-framework-for-adapter-configuration"></a><span data-ttu-id="8e91d-133">Utilizar el marco de trabajo de la configuración de adaptador</span><span class="sxs-lookup"><span data-stu-id="8e91d-133">Using the Framework for Adapter Configuration</span></span>  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8e91d-134">Proporciona un mecanismo para generar hojas de propiedades para la interfaz de usuario de configuración de adaptador (UI).</span><span class="sxs-lookup"><span data-stu-id="8e91d-134"> provides a mechanism for generating property sheets for the adapter configuration user interface (UI).</span></span> <span data-ttu-id="8e91d-135">Se basa en una definición del lenguaje de definición de esquemas XML (XSD) de las propiedades de configuración.</span><span class="sxs-lookup"><span data-stu-id="8e91d-135">It is based on an XML Schema Definition (XSD) definition of the configuration properties.</span></span> <span data-ttu-id="8e91d-136">La utilización de este marco de trabajo presenta retos significativos para el programador de adaptadores.</span><span class="sxs-lookup"><span data-stu-id="8e91d-136">The use of this framework introduces significant challenges for the adapter developer.</span></span> <span data-ttu-id="8e91d-137">Esta sección sugiere una solución efectiva para algunos de estos problemas.</span><span class="sxs-lookup"><span data-stu-id="8e91d-137">This section suggests an effective workaround for some of these issues.</span></span>  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a><span data-ttu-id="8e91d-138">Considerar editores de propiedades personalizados para todas las propiedades clave</span><span class="sxs-lookup"><span data-stu-id="8e91d-138">Consider Custom Property Editors for all Your Key Properties</span></span>  
 <span data-ttu-id="8e91d-139">No es posible colocar la validación de propiedad significativa en la parte superior de propiedades en la hoja de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8e91d-139">It is impossible to put significant property validation on top of properties in the property sheet.</span></span> <span data-ttu-id="8e91d-140">El marco de trabajo trata de utilizar las restricciones simpleType del lenguaje de definición de esquemas XML (XSD) para definir las reglas de validación de la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8e91d-140">The framework attempts to use XML Schema Definition (XSD) simpleType restrictions to define the validation rules for the UI.</span></span> <span data-ttu-id="8e91d-141">Las reglas simples para los valores máximo y mínimo se aplican aunque la restricción de la expresión habitual para los campos de cadena no sea compatible.</span><span class="sxs-lookup"><span data-stu-id="8e91d-141">The simple rules for maximum and minimum value are applied but the regular expression restriction for string fields is not supported.</span></span> <span data-ttu-id="8e91d-142">Además, los datos se convierten en tipos de Common Language Runtime (CLR) antes de que se aplique la restricción.</span><span class="sxs-lookup"><span data-stu-id="8e91d-142">Also, the data is converted into common language runtime (CLR) types before the restriction is applied.</span></span> <span data-ttu-id="8e91d-143">Esto significa que el usuario de la interfaz a veces obtiene un error de conversión más bien de tipo críptico que un error de fuera de intervalo.</span><span class="sxs-lookup"><span data-stu-id="8e91d-143">This means the user of the UI sometimes gets a cryptic type-conversion error rather than an out-of-range error.</span></span> <span data-ttu-id="8e91d-144">Con todo, la lógica de validación es muy débil.</span><span class="sxs-lookup"><span data-stu-id="8e91d-144">All in all, the validation logic is very weak.</span></span>  
  
 <span data-ttu-id="8e91d-145">La solución que han adoptado numerosos programadores de adaptadores es escribir editores de propiedades personalizados para las propiedades principales de la hoja de propiedades.</span><span class="sxs-lookup"><span data-stu-id="8e91d-145">The solution many adapter developers have adopted is to write custom property editors for the main properties on their property sheet.</span></span> <span data-ttu-id="8e91d-146">Si hay un número de propiedades que dependen de referencias cruzadas (como sucede a menudo), el editor de propiedades de carácter personalizado puede combinar los resultados en un único campo y el tiempo de ejecución puede separarlos posteriormente.</span><span class="sxs-lookup"><span data-stu-id="8e91d-146">If there are a number of cross-dependent properties (as is often the case), then the custom property editor can combine the results into a single field and the runtime can later separate them.</span></span> <span data-ttu-id="8e91d-147">Ésta es la única forma de especificar el código personalizado necesario (aunque continúa siendo por lo general trivial) en la interfaz.</span><span class="sxs-lookup"><span data-stu-id="8e91d-147">This is the only way to get the necessary (though still generally trivial) custom code into the interface.</span></span>  
  
 <span data-ttu-id="8e91d-148">Los editores de propiedades de carácter personalizado son relativamente sencillos de escribir y la propiedad de XSD se puede anotar para utilizarlas.</span><span class="sxs-lookup"><span data-stu-id="8e91d-148">Custom property editors are relatively straightforward to write and the property in the XSD can be annotated to use them.</span></span> <span data-ttu-id="8e91d-149">La anotación hace referencia a un ensamblado que expone el punto de entrada del editor de propiedades y se codifica para mostrar un formulario CLR.</span><span class="sxs-lookup"><span data-stu-id="8e91d-149">The annotation references an assembly that exposes the property editor entry point, and it is coded to show a CLR Form.</span></span> <span data-ttu-id="8e91d-150">Ahora puede escribir una interfaz de usuario habitual y utilizar las herramientas de generación de la interfaz que ofrece Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8e91d-150">You can now write a regular user interface and use the traditional interface-generation tools that Visual Studio offers.</span></span>  
  
 <span data-ttu-id="8e91d-151">En el siguiente código se muestra cómo utilizar XSD para agregar un editor de propiedades de carácter personalizado:</span><span class="sxs-lookup"><span data-stu-id="8e91d-151">The following code shows how to use the XSD to add a custom property editor:</span></span>  
  
```  
<xs:element name="queueDetails" type="xs:string" minOccurs="0">  
    <xs:annotation>  
        <xs:appinfo>  
           <baf:designer>  
               <baf:displayname _locID="queueName">Queue Definition</baf:displayname>  
               <baf:description _locID="receiveQueueDesc">Details of MQSeries Server, Queue Manager and Queue from where you want to receive messages.</baf:description>  
               <baf:category _locID="mqsCategory">MQSeries</baf:category>  
               <baf:editor assembly="Microsoft.BizTalk Server.Adapter.MQSAdmin.dll">Microsoft.BizTalk Server.Adapter.MQSAdmin.MQSUITypeEditor</baf:editor>  
            </baf:designer>  
        </xs:appinfo>  
    </xs:annotation>  
</xs:element>  
  
```  
  
 <span data-ttu-id="8e91d-152">El código al que se hace referencia debe tener el mismo aspecto que éste:</span><span class="sxs-lookup"><span data-stu-id="8e91d-152">The code that is referenced should look like this:</span></span>  
  
```  
public class MQSUITypeEditor : System.Drawing.Design.UITypeEditor  
{  
public override System.Drawing.Design.UITypeEditorEditStyle GetEditStyle  
(System.ComponentModel.ITypeDescriptorContext context)   
{  
return System.Drawing.Design.UITypeEditorEditStyle.Modal;  
}  
public override object EditValue (System.ComponentModel.ITypeDescriptorContext context,  
System.IServiceProvider provider, object value)   
{  
Form qdForm = new QueueDefinitionForm(value);  
IWindowsFormsEditorService service =   
(IWindowsFormsEditorService)provider.GetService(typeof(IWindowsFormsEditorService));  
DialogResult dialogResult = service.ShowDialog(qdForm);  
//…  
}  
}  
class QueueDefinitionForm : System.Windows.Forms.Form   
{  
//  traditional UI code goes here!  
}  
  
```  
  
 <span data-ttu-id="8e91d-153">El tiempo de ejecución de administración debe estar habilitado para encontrar el ensamblado al que se hace referencia en XSD, de modo que debe agregarlo a la caché de ensamblado global.</span><span class="sxs-lookup"><span data-stu-id="8e91d-153">The administration runtime must be able to find the assembly referenced in the XSD, so you should add it to the global assembly cache.</span></span>