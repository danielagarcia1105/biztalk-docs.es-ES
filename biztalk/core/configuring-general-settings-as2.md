---
title: Configuración General (AS2) | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8592c52e-5156-418c-9c49-7478f73c372e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20a0fa1ea7e9a3c6462f09eddee564850c4820dd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001453"
---
# <a name="configuring-general-settings-as2"></a>Configuración general (AS2)
Como parte de la configuración general, se especifica el nombre del acuerdo, el protocolo que usará (AS2), las entidades y perfiles entre los que se produce el acuerdo, así como si estará habilitada la notificación de todos los mensajes procesados mediante el acuerdo. También puede especificar la información de contacto de las entidades como parte del acuerdo.  

## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

### <a name="to-configure-general-agreement-settings"></a>Para configurar el acuerdo general  

1. En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **partes** en el árbol de consola y, en el **entidades y perfiles empresariales** página, haga clic en un perfil de negocio que debe formar parte del acuerdo que está creando, seleccione **New**y, a continuación, haga clic en **contrato**.  

2. Las siguientes tablas enumeran las distintas propiedades y los valores que se puede especificar para las propiedades en el **propiedades generales** página.  

   1. En el **parámetros del acuerdo** sección, realice lo siguiente:  


      |   Use   |                                                                                                     Para                                                                                                     |
      |--------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |   **Nombre**   |                                                                                          Especifique un nombre para el acuerdo.                                                                                          |
      |    **ID**    |               Se enumera la identificación única del acuerdo. Este cuadro de texto no es editable y mostrará el identificador del contrato tras hacer clic en **aplicar** para que se acepta la primera vez y configuración.               |
      |  **Estado**  | Especifica el estado del acuerdo. De forma predeterminada, se crea un acuerdo en un **Active** estado. Si desea que el acuerdo esté deshabilitado cuando se cree, seleccione **deshabilitado** en la lista desplegable. |
      | **Protocolo** |                                                  Especifica el protocolo para el acuerdo. Para un protocolo de transporte AS2, seleccione **AS2** en la lista desplegable.                                                  |


   2. En el **primer socio** sección, realice lo siguiente:  


      |     Use     |                                                                                                      Para                                                                                                       |
      |------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **Nombre**     |                                           Muestra el nombre del socio comercial que tiene el perfil empresarial para el que se crea el acuerdo. Este cuadro de texto no es editable.                                            |
      |   **Perfil**    |                                                       Muestra el nombre del perfil para el que se crea el acuerdo. Este cuadro de texto no es editable.                                                       |
      | **Conjunto de protocolos** | Si ha creado un conjunto de protocolos AS2 como parte del perfil de negocio, puede seleccionarlo en la lista desplegable. Si no ha creado ningún conjunto de protocolos AS2 como parte del perfil de negocio, puede dejarlo en blanco. |


   3. En el **segundo socio** sección, realice lo siguiente:  

      |Use|Para|  
      |--------------|----------------|  
      |**Nombre**|En la lista desplegable, seleccione una entidad que tenga el perfil empresarial con el que desea crear un acuerdo.|  
      |**Perfil**|En la lista desplegable, seleccione un perfil con el que desea crear un acuerdo.|  
      |**Conjunto de protocolos**|Si ha creado un conjunto de protocolos AS2 como parte del perfil de negocio, puede seleccionarlo en la lista desplegable. Si no ha creado ningún conjunto de protocolos AS2 como parte del perfil de negocio, puede dejarlo en blanco.|  

      > [!TIP]
      >  Presione `CTRL`, seleccione los perfiles de negocio que formar parte del acuerdo, haga clic en cualquiera de los perfiles empresariales, elija **New**y, a continuación, haga clic en **contrato**. Los valores de nombre de asociado y perfiles de negocio de ambos socios se rellenarán automáticamente en el **las propiedades del acuerdo** cuadro de diálogo.  

      > [!NOTE]
      >  Tan pronto como seleccione el otro perfil, se agregarán dos fichas junto a la **General** ficha. Cada ficha representa un acuerdo AS2 unidireccional entre las dos entidades. Se usan las fichas para especificar la configuración relacionada con el intercambio y el conjunto de transacciones.  

   4. Seleccione el **habilitar acuerdo** casilla de verificación para habilitar el acuerdo y realice lo siguiente:  


      |    Use     |                                        Para                                         |
      |-----------------|-------------------------------------------------------------------------------------------|
      |    **De**     |             Seleccione la fecha y hora desde la que será válido el acuerdo.              |
      | **Sin fecha de finalización** | Seleccione esta opción si no desea establecer una fecha de finalización en la que se deshabilite el acuerdo.  |
      |   **Finalizar el**    | Seleccione esta opción y especifique la fecha y hora hasta la que el acuerdo será válido. |


   5. En el **configuración de Host común** sección, realice lo siguiente:  


      |       Use        |                                                                                                                                                          Para                                                                                                                                                          |
      |-----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      | **Activar los informes** | para mostrar las entradas de estado para todos los mensajes AS2 (entrantes o salientes) en el **mensaje AS2 y estado de MDN correlacionado** pestaña de la **información general del grupo** panel en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Si no está activada, no se mostrarán entradas de estado. |


3. En el **General** ficha la **información de contacto** página, realice lo siguiente:  

   1.  En el **contacto1** , escriba la información de contacto para el perfil de la entidad con la que se crea un acuerdo. Estos datos se proporcionan con fines informativos únicamente. El tiempo de ejecución de BizTalk no los utilizará.  

   2.  Para agregar otra ficha de contacto, haga clic en el **nuevo contacto** ficha.  

   3.  Para eliminar una ficha de contacto, haga clic en **eliminar** desde la esquina superior derecha de la página de ficha.  

       > [!NOTE]
       >  No puede eliminar el **contacto1** ficha. Solo se pueden eliminar las fichas nuevas que agregue.  

4. En el **General** ficha la **propiedades adicionales** página, realice lo siguiente:  

   > [!NOTE]
   >  BizTalk Server no usará la información que especifique en esta página para ningún proceso; estos datos son solo para fines informativos.  

   1.  En el **propiedades adicionales** cuadrícula, escriba los pares nombre / valor para toda la información que desea agregar en relación con la entidad o el acuerdo.  Escriba un par nombre-valor para almacenar cualquier información sobre la entidad. Puede agregar tantos pares nombre-valor como desee.  

        Para eliminar un par nombre-valor, seleccione la fila y haga clic en **eliminar** desde la esquina superior derecha.  

   2.  En el **texto 1**, **texto 2**, y **acuerdo** cuadros de texto, escriba la información sobre el acuerdo con una entidad.  

       > [!IMPORTANT]
       >  Si hace clic en **Aceptar** o **aplicar** después de proporcionar todos los valores enumerados en esta página, obtendrá un error. Es así porque aún no se han proporcionado los valores obligatorios para crear un acuerdo. Se trata de AS2-de para AS2-a valores en el **identificadores** página de cada ficha de acuerdo unidireccional.  

## <a name="next-steps"></a>Pasos siguientes  
 Ahora debe configurar las opciones del identificador para el acuerdo. Para obtener instrucciones, consulte [configurar identificadores (AS2)](../core/configuring-identifiers-as2.md).  

## <a name="see-also"></a>Vea también  
 [Configuración de las propiedades de acuerdo AS2](../core/configuring-as2-agreement-properties.md)