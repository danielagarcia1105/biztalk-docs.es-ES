---
title: Cómo exportar enlaces para una solución EDI y AS2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 856ab630-66c4-4496-884a-fdbe641143c5
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36bd9c265d28555c40f84f1728fd28846fbd516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012333"
---
# <a name="how-to-export-bindings-for-an-edi-as2-solution"></a>Cómo exportar enlaces para una solución EDI y AS2
En este tema se describe cómo exportar la configuración de un equipo configurado como solución EDI y/o AS2. Permite definir la misma configuración en otro equipo de forma automática. Puede exportar los enlaces desde una aplicación, un grupo o un ensamblado.  
  
 Un archivo de enlace se crea desde la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El archivo de enlace .xml contiene toda la información pertinente para la configuración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Esto incluye todas las propiedades de configuración de EDI y AS2, con la excepción de cierta información de seguridad. Para obtener información detallada acerca de los nodos en un archivo de enlace (nodos EDI y AS2 incluidos), consulte [estructura de un archivo de enlace](../core/structure-of-a-binding-file.md). Para obtener información general sobre los vínculos EDI/AS2, consulte "Nodos EDI y AS2 en el archivo de enlace de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]" a continuación.  
  
 También puede exportar enlaces como parte de la exportación de una aplicación mediante un archivo .msi. Para obtener más información, consulte el [cómo exportar una aplicación de BizTalk](../core/how-to-export-a-biztalk-application.md). También puede utilizar el comando BTSTask para exportar e importar enlaces. Para obtener más información acerca de BTSTask, vea [referencia de línea de comandos de BTSTask](../core/btstask-command-line-reference.md).  
  
 **Exportación de enlaces**  
  
 Al exportar la configuración, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] exportará de forma automática las propiedades EDI y otra información de entidades de todas las entidades enlazadas. Si activa la exportación de la información de entidad global, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también exportará las propiedades de las entidades que no estén enlazadas con la orquestación y las propiedades EDI globales. Puede exportar información de entidad global de tres formas distintas:  
  
- Activando la propiedad Exportar información de entidad global en el cuadro de diálogo Exportar enlaces.  
  
- Activando la casilla de verificación Entidades globales en el panel Seleccionar recursos del Asistente para exportación de archivos MSI.  
  
- Utilizando el conmutador GlobalParties de la herramienta de línea de comandos BTSTask del modo que se muestra a continuación:  
  
  ```  
  BTSTask ExportBindings -Destination:value ((([-ApplicationName:value] | [-AssemblyName:value]) [-GlobalParties]) | [-GroupLevel])  
  ```  
  
  Por motivos de seguridad, al exportar un archivo de enlace, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] quita las contraseñas para los enlaces del archivo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Quita los campos UNB6.1 y UNB6.2 de las propiedades de EDIFACT y los campos ISA1, ISA2, ISA3 e ISA4 de X12 propiedades.  
  
  Además de utilizar los comandos export-bindings, export-application o BTSTask, puede crear un archivo de enlace XML de forma manual. Al hacerlo, puede exportar la configuración de EDI y de entidad desde una aplicación de línea empresarial. A continuación, podría importar los enlaces mediante el comando import-bindings o el comando BTSTask.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe haber iniciado sesión con una cuenta que sea miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Para obtener más información, consulte "Permisos necesarios para la implementación y administración de aplicaciones de BizTalk" en la documentación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="exporting-the-configuration-into-a-binding-file"></a>Exportar la configuración a un archivo de enlace  
  
1. En el equipo desde el que desea exportar la configuración, abra la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
2. Haga clic en la aplicación de BizTalk que desea copiar la configuración de, seleccione **exportar**y, a continuación, haga clic en **enlaces**.  
  
   > [!NOTE]
   >  También puede utilizar la utilidad BTSTask para exportar o importar la configuración.  
  
3. Seleccione la opción de exportación e indique que la exportación se va a realizar desde la aplicación o el grupo actual, o bien exportando los enlaces de un ensamblado.  
  
4. Si desea exportar todas las entidades y sus propiedades no confidenciales, incluso si una orquestación no está enlazada a ellas, haga clic en **información de entidad Global exportar**.  
  
   > [!NOTE]
   >  Si no hace clic en **información de entidad Global exportar**, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] exportará las propiedades de todas las entidades que están enlazadas a una orquestación, en el archivo de enlace. Sin embargo, no exportará todas las entidades que no están enlazadas a una orquestación, a menos que haga clic en **información de entidad Global exportar**.  
   > 
   > [!NOTE]
   >  El archivo de enlace generado mientras la **información de entidad Global exportar** está seleccionada la propiedad incluirá la configuración de todas las entidades definidas en el equipo. No es posible exportar la configuración de un subconjunto del conjunto completo de entidades definido en un equipo.  
  
5. Haga clic en **Aceptar** para exportar los enlaces.  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no exportará ningún campo confidencial de EDI, como contraseñas o información de autenticación o seguridad. Exportará una cadena en blanco por cada campo confidencial de EDI. Tras importar los enlaces en otro equipo, debe establecer manualmente los valores de los campos confidenciales de EDI.  
  
6. Anote manualmente todos los campos confidenciales de EDI, como las contraseñas o la información de autenticación o seguridad para definirlos más tarde en el equipo en el que esté importando los enlaces.  
  
## <a name="edi-and-as2-nodes-in-the-biztalk-server-binding-file"></a>Nodos EDI y AS2 en el archivo de enlace de BizTalk Server  
 Si exporta la configuración con la **información de entidad Global exportar** propiedad seleccionada, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generará un archivo de enlace que tenga los siguientes nodos:  
  
```  
EdiData  
   PartyEDIProperties  
      PartnerAgreement  
         Contacts  
      PartnerEdifact  
         PartnerEdifactReceiverGroups  
         PartnerEdifactSenderGroups  
      PartnerAckValidation  
      PartnerX12  
      PartnerX12ReceiverGroups  
      PartnerX12SenderGroups  
      PartnerBatchUpdatable  
      PartnerAS2CommonUpdatable  
      PartnerAS2  
```  
  
 Las propiedades globales de EDI se agregarán al archivo de enlace en los nodos siguientes.  
  
```  
EDIGlobalProperties  
   EDIGlobalProperties  
      GlobalCommon  
      GlobalEdiFact  
      GlobalX12  
```  
  
 Los nodos EDI y AS2 se agregan al final del archivo de enlace de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. El nodo EdiData se agrega al subnodo Entidad bajo el nodo Colección de entidades y el nodo EdiGlobalProperties se agregará más tarde y al mismo nivel que el nodo Colección de entidades. Para obtener más información acerca de los nodos EDI y AS2 en el archivo de enlace de BizTalk, consulte [estructura de un archivo de enlace](../core/structure-of-a-binding-file.md).  
  
 El nodo EdiData es opcional. Sin embargo, si el nodo EdiData está presente, serán necesarios los subnodos de EdiData. De forma similar, el nodo EdiGlobalProperties es opcional; sin embargo, si está presente el nodo EdiGlobalProperties, serán necesarios los subnodos de éste.  
  
 Los nodos del archivo de enlace de EDI y AS2 no corresponden directamente con las páginas de propiedades del Administrador de acuerdos de socios comerciales en la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Algunos nodos del archivo de enlace de EDI y AS2 incluyen propiedades utilizadas para las funciones de remitente y propiedades utilizadas para las funciones del receptor. La propiedad IsSender en el nodo indica la función. Para los nodos que no se utilicen para funciones de remitente y receptor (PartnerAgreement, PartnerBatchUpdatable, PartnerAS2Updatable y GlobalCommon), IsSender tendrá siempre el valor False.  
  
 Los nodos PartnerEdifact y PartnerX12 contienen propiedades para funciones de remitente y receptor, independientemente de que IsSender esté definido como True o False. Por ejemplo, PartnerEdifact incluirá un campo Una1 (utilizado para la entidad como receptor de intercambio), incluso si IsSender tiene el valor True. Por ejemplo, PartnerEdifact incluirá un campo Unb5CheckDup (utilizado para la entidad como remitente de intercambio), incluso si IsSender tiene el valor False. Sin embargo, si IsSender tiene el valor True, los campos de la entidad como receptor de intercambio no se utilizan en la IU ni en el motor, pero se ofrecen como valores predeterminados. De forma similar, si IsSender tiene el valor False, los campos de la entidad como remitente de intercambio no se utilizan en la IU ni en el motor, pero se ofrecen como valores predeterminados.  
  
 Si el valor predeterminado de una propiedad es nulo, el campo no se incluirá en el archivo de enlace a menos que se le haya otorgado un valor al campo.  
  
 Los datos del archivo de enlace se guardan en tablas de la base de datos de administración de BizTalk (BizTalkMgmtDb).