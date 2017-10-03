---
title: "Cómo implementar un adaptador personalizado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f17b336c-6232-4889-ab7e-92b83fab0f5f
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e36443b99f01688a38e66a4a302ab64bb220092f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-deploy-a-custom-adapter"></a>Cómo implementar un adaptador personalizado
Un proceso completo de instalación de adaptador se compone de los siguientes pasos:  
  
1.  Comprobar dependencias. Por ejemplo, el instalador del adaptador de MSMQ comprueba la existencia del servicio local de MSMQ, ya que el tiempo de ejecución del adaptador depende de ello.  
  
2.  Configurar el sistema de archivos local. Incluye la creación de carpeta de instalación y la copia de archivos de compatibilidad y binarios. Asegúrese de que tiene acceso a las carpetas y que los permisos de acceso de archivo se han configurado adecuadamente.  
  
3.  Instalar ensamblados administrados en la caché de ensamblados global del sistema.  
  
4.  Crear claves del Registro para el adaptador.  
  
    > [!NOTE]
    >  Para un adaptador de 32 bits, la consola de administración de BizTalk Server utiliza la rama HKEY_CLASSES_ROOT del Registro para obtener una configuración de adaptador personalizada.  Si un adaptador de 32 bits se instala en un servidor de 64 bits, la consola de administración de BizTalk Server utilizará la rama HKEY_CLASSES_ROOT\Wow6432Node\ para los datos de configuración de adaptador.  
  
5.  Agregar el adaptador a BizTalk Server. Esto significa que las nuevas entradas de la base de datos de administración de BizTalk del adaptador y del esquema de propiedades se han utilizado para reflejar propiedades promovidas por el adaptador. Este paso se realiza a veces manualmente con la consola de administración de BizTalk Server.  
  
## <a name="exceptions"></a>Excepciones  
 Es posible que el instalador de adaptador no tenga que comprobar las dependencias en las instalaciones parciales de BizTalk Server. Por ejemplo, en una instalación solo de herramientas administrativas no es necesario comprobar las dependencias del tiempo de ejecución del adaptador, ya que el tiempo de ejecución del adaptador no se utiliza. Lo mismo sucede en la instalación solo de tiempo de ejecución de BizTalk Server, en la que no es necesario que el instalador de adaptador compruebe las dependencias de tiempo de diseño de adaptador.  
  
 En varios entornos de BizTalk Server, el último paso de la lista anterior (Agregar el adaptador a BizTalk Server) solo se realiza en la instalación de adaptador del primer servidor BizTalk Server. Esto sucede porque todas las instancias del servicio de BizTalk Server comparten la misma base de datos de administración de BizTalk (con el nombre predeterminado BizTalkMgmtDB). Si los adaptadores se han agregado a otros servidores de BizTalk Server del mismo grupo, los pasos adicionales producirán un error.  
  
## <a name="install-the-adapter-assemblies-into-the-global-assembly-cache"></a>Instalar los ensamblados de adaptador en la caché de ensamblados global  
 Para compatibilizar varios entornos de host de BizTalk Server con diferentes rutas de instalación de adaptador, los ensamblados de adaptador deben instalarse en la caché de ensamblados global del sistema.  
  
 Durante la instalación y configuración de adaptador, se crea una nueva entrada de adaptador en la tabla adm_adapter de la base de datos de administración de BizTalk (con el nombre predeterminado BizTalkMgmtDB). Esta entrada contiene toda la información de referencia utilizada por BizTalk Server durante el tiempo de ejecución y el tiempo de diseño.  
  
 El **InBoundAssemblyPath** y **OutboundAssemblyPath** campos se usan en tiempo de ejecución de BizTalk Server para averiguar dónde se deben cargar los archivos binarios del adaptador. Puesto que solo hay una base de datos de administración de BizTalk para un grupo de BizTalk Server, todos los servidores de BizTalk Server del grupo deben compartir esta misma información. Si desea instalar el adaptador en diferentes servidores de BizTalk Server dentro del grupo, debe utilizar la misma ruta de instalación en cada uno de los servidores. Si la ruta de instalación local es diferente de la ruta almacenada en la base de datos de administración de BizTalk, BizTalk Server no puede cargar los binarios de adaptadores.  
  
 Firme siempre el ensamblado de adaptador con un nombre seguro y utilice Gacutil.exe para colocar el ensamblado de adaptador en la caché de ensamblados global del sistema durante la instalación del adaptador. Asegúrese de que deje el **InBoundAssemblyPath** y **OutboundAssemblyPath** campos null ni estar vacíos.  
  
## <a name="using-the-framework-for-adapter-configuration"></a>Utilizar el marco de trabajo de la configuración de adaptador  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Proporciona un mecanismo para generar hojas de propiedades para la interfaz de usuario de configuración de adaptador (UI). Se basa en una definición del lenguaje de definición de esquemas XML (XSD) de las propiedades de configuración. La utilización de este marco de trabajo presenta retos significativos para el programador de adaptadores. Esta sección sugiere una solución efectiva para algunos de estos problemas.  
  
### <a name="consider-custom-property-editors-for-all-your-key-properties"></a>Considerar editores de propiedades personalizados para todas las propiedades clave  
 No es posible colocar la validación de propiedad significativa en la parte superior de propiedades en la hoja de propiedades. El marco de trabajo trata de utilizar las restricciones simpleType del lenguaje de definición de esquemas XML (XSD) para definir las reglas de validación de la interfaz. Las reglas simples para los valores máximo y mínimo se aplican aunque la restricción de la expresión habitual para los campos de cadena no sea compatible. Además, los datos se convierten en tipos de Common Language Runtime (CLR) antes de que se aplique la restricción. Esto significa que el usuario de la interfaz a veces obtiene un error de conversión más bien de tipo críptico que un error de fuera de intervalo. Con todo, la lógica de validación es muy débil.  
  
 La solución que han adoptado numerosos programadores de adaptadores es escribir editores de propiedades personalizados para las propiedades principales de la hoja de propiedades. Si hay un número de propiedades que dependen de referencias cruzadas (como sucede a menudo), el editor de propiedades de carácter personalizado puede combinar los resultados en un único campo y el tiempo de ejecución puede separarlos posteriormente. Ésta es la única forma de especificar el código personalizado necesario (aunque continúa siendo por lo general trivial) en la interfaz.  
  
 Los editores de propiedades de carácter personalizado son relativamente sencillos de escribir y la propiedad de XSD se puede anotar para utilizarlas. La anotación hace referencia a un ensamblado que expone el punto de entrada del editor de propiedades y se codifica para mostrar un formulario CLR. Ahora puede escribir una interfaz de usuario habitual y utilizar las herramientas de generación de la interfaz que ofrece Visual Studio.  
  
 En el siguiente código se muestra cómo utilizar XSD para agregar un editor de propiedades de carácter personalizado:  
  
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
  
 El código al que se hace referencia debe tener el mismo aspecto que éste:  
  
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
  
 El tiempo de ejecución de administración debe estar habilitado para encontrar el ensamblado al que se hace referencia en XSD, de modo que debe agregarlo a la caché de ensamblado global.