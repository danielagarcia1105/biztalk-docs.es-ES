---
title: Administración de contratos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.resultsobject.agreement
ms.assetid: e9c6cdd1-8c17-4b1e-a556-2b287593bb9d
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 012a4a5032bd9f9e9a66b855d41a83b5dc5736d1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="managing-agreements"></a>Administración de acuerdos
Un acuerdo de socios comerciales (TPA) se define como un acuerdo vinculante y definitivo entre dos socios comerciales para la transacción de mensajes a través de un protocolo B2B específico. Vea [acuerdo de socio comercial](../core/trading-partner-agreement.md). 

Estos temas se muestra cómo crear, ver, editar, habilitar, deshabilitar o eliminar un acuerdo.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="create-an-agreement"></a>Crear un acuerdo  
  
1.  Abra **administración de BizTalk Server**, expanda el grupo de BizTalk y seleccione **partes**. 
2. En el **entidades y perfiles empresariales** página, haga clic en un perfil de negocio que forma parte del acuerdo que está creando, seleccione **New**y, a continuación, seleccione **acuerdo**.  
  
3.  En el **propiedades generales**: 
  
    1.  En el **parámetros del acuerdo** sección, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|Escriba un nombre para el acuerdo|  
        |**ID**|Se enumera la identificación única del acuerdo. Este cuadro de texto es de solo lectura y mostrar el identificador del acuerdo después de seleccionar **aplicar** para la primera hora y la configuración se acepta.|  
        |**Estado**|Especifica el estado del acuerdo. De forma predeterminada, se crea un acuerdo en un **Active** estado. Si desea que el acuerdo para estar deshabilitado cuando se cree, seleccione **deshabilitado** en la lista desplegable.|  
        |**Protocolo**|Especifica el protocolo para el acuerdo.<br /><br /> -Para un X12 protocolo de codificación, seleccione **X12** en la lista desplegable. Vea [configurar propiedades de acuerdos específicos de X12](../core/configuring-x12-specific-agreement-properties.md)<br />-Para un protocolo de codificación de EDIFACT, seleccione **EDIFACT** en la lista desplegable.  Vea [configuración de las propiedades de acuerdos específicos de EDIFACT](../core/configuring-edifact-specific-agreement-properties.md).<br />-Para un protocolo de codificación AS2, seleccione **AS2** en la lista desplegable. Vea [configurar propiedades del acuerdo AS2](../core/configuring-as2-agreement-properties.md). <br/><br/>**Nota**<br/>  Las propiedades del acuerdo se proporcionan en las fichas de acuerdo unidireccional. Las fichas de acuerdo unidireccional aparecen una vez se ha seleccionado el segundo perfil con el que se creará el acuerdo. Seleccione el segundo socio comercial en los pasos siguientes.|  
  
    2.  En el **primer socio comercial** sección, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|Muestra el nombre del socio comercial que tiene el perfil empresarial para el que se crea el acuerdo. Este cuadro de texto es de solo lectura.|  
        |**Perfil**|Muestra el nombre del perfil para el que se crea el acuerdo. Este cuadro de texto es de solo lectura.|  
        |**Conjunto de protocolos**|Si ha creado un conjunto de protocolos X12 como parte del perfil empresarial, puede seleccionarlo en la lista desplegable. Si no ha creado ningún conjunto de protocolos X12 como parte del perfil empresarial, puede dejarlo en blanco.|  
  
    3.  En el **segundo socio** sección, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Nombre**|En la lista desplegable, seleccione una entidad que tenga el perfil empresarial con el que desea crear un acuerdo.|  
        |**Perfil**|En la lista desplegable, seleccione un perfil con el que desea crear un acuerdo.|  
        |**Conjunto de protocolos**|Si ha creado un conjunto de protocolos X12 como parte del perfil empresarial, puede seleccionarlo en la lista desplegable. Si no ha creado ningún conjunto de protocolos X12 como parte del perfil empresarial, puede dejarlo en blanco.|  
  
        > [!TIP]
        >  Presione `CTRL`, seleccione los perfiles empresariales que pueden formar parte del acuerdo, haga clic en cualquier perfil de negocio, seleccione **New**y, a continuación, seleccione **acuerdo**. Los valores de nombre de socios y perfiles de negocio de ambos socios se rellenarán automáticamente en el **propiedades del acuerdo de** cuadro de diálogo.  
  
        > [!NOTE]
        >  Tan pronto como seleccione el perfil de otro, se agregarán dos fichas junto a la **General** ficha. Cada ficha representa un acuerdo unidireccional entre dos entidades. Utilice las fichas para especificar las propiedades del acuerdo.  
  
    4.  Seleccione el **habilitar acuerdo** casilla de verificación para habilitar el acuerdo y realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**De**|Seleccione la fecha y hora desde el que será válido el acuerdo.|  
        |**Sin fecha de finalización**|Seleccione esta opción si no desea establecer una fecha de finalización en la que se deshabilite el acuerdo.|  
        |**Finalizar el**|Seleccione esta opción para especificar la fecha y hora hasta que el acuerdo es válido.|  
  
    5.  En el **configuración de Host común** sección, realice lo siguiente:  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Registrar errores en el registro de eventos**|Seleccione esta opción para registrar los mensajes de error generados por el motor de EDI (canalizaciones de EDI, orquestación de procesamiento por lotes, orquestación de enrutamiento, etc.) junto con información contextual en el Visor de eventos de Windows.<br/><br/>**Tenga en cuenta**: no se aplica a los acuerdos de AS2.|  
        |**Registrar advertencias en el registro de eventos**|Seleccione esta opción para registrar los mensajes de advertencia generados por el motor de EDI (canalizaciones de EDI, orquestación de procesamiento por lotes, orquestación de enrutamiento, etc.) junto con información contextual en el Visor de eventos de Windows. <br/><br/>**Tenga en cuenta**: no se aplica a los acuerdos de AS2.|  
        |**Activar los informes de**|Seleccione esta opción para mostrar las entradas de estado para todos los mensajes EDI (entrantes o salientes) en el **intercambio EDI y estado de confirmación correlacionado** pestaña de la **información general del grupo** página en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración. Si no está activada, no se muestran entradas de estado.|  
        |**Almacenar carga de mensaje para informes**|Si seleccionó **activar informes**, seleccione esta opción para almacenar transacciones se establece en las tablas EDI de la base de datos de seguimiento (BizTalkDTADb). <br/><br/>**Tenga en cuenta**: no se aplica a los acuerdos de AS2.|  
  
4.  En el **General** ficha la **información de contacto** página, realice lo siguiente:  
  
    1.  En el **contacto1** ficha, escriba la información de contacto para el perfil de la entidad con la que va a crear un acuerdo. Estos datos son meramente informativo; no se usa el Runtime de BizTalk.  
  
    2.  Para agregar otra ficha de contacto, seleccione el **nuevo contacto** ficha.  
  
    3.  Para eliminar una ficha de contacto, seleccione **eliminar** desde la esquina superior derecha de la página de fichas.  
  
        > [!NOTE]
        >  No se puede eliminar el **contacto1** ficha. Solo se pueden eliminar las fichas nuevas que agregue.  
  
5.  En el **General** ficha la **propiedades adicionales** página, realice lo siguiente:  
  
    > [!NOTE]
    >  La información que especifique en esta página no se utiliza el servidor de BizTalk para ningún proceso; estos datos son solo para fines informativos.  
  
    1.  En el **propiedades adicionales** cuadrícula, escriba los pares nombre / valor para toda la información que desea agregar relacionados con la entidad o el acuerdo.  Escriba un par nombre-valor para almacenar cualquier información sobre la entidad. Puede agregar tantos pares nombre-valor como desee.  
  
         Para eliminar un par nombre-valor, seleccione la fila y seleccione **eliminar** desde la esquina superior derecha.  
  
    2.  En el **texto 1**, **texto 2**, y **acuerdo** cuadros de texto, escriba la información sobre el acuerdo con una entidad.  
  
    3.  Seleccione **aplicar** para aceptar las propiedades o seleccione **Aceptar** para completar la configuración. Cualquiera de estas acciones valida la configuración.  

## <a name="view-or-change-an-agreement"></a>Ver o cambiar un acuerdo  
  
1.  En **administración de BizTalk Server**, seleccione **partes**. 

2. En el **entidades y perfiles empresariales** página, seleccione cualquiera de los dos perfiles de negocio que contienen el acuerdo que desea ver o editar.  
  
3.  En el **contratos** sección, haga clic en el acuerdo y, a continuación, seleccione **propiedades**.  
  
4.  En el **propiedades del acuerdo**, ver o editar el contrato. Para los valores que pueden escribirse en las distintas fichas y páginas en el **propiedades del acuerdo** diálogo cuadro, vea lo siguiente:  
  
    |Para|Consulte|  
    |--------------|--------------|  
    |Para el acuerdo X12|[Configurar propiedades de acuerdos específicos de X12](../core/configuring-x12-specific-agreement-properties.md)|  
    |Para el acuerdo EDIFACT|[Configuración de las propiedades de acuerdos específicos de EDIFACT](../core/configuring-edifact-specific-agreement-properties.md)|  
    |Para el acuerdo AS2|[Configurar propiedades del acuerdo de AS2](../core/configuring-as2-agreement-properties.md)|  
  
5.  Seleccione **aplicar** para aceptar las propiedades o seleccione **Aceptar** para completar la configuración. Cualquiera de estas acciones valida la configuración. 

## <a name="enable-or-disable-an-agreement"></a>Habilitar o deshabilitar un acuerdo  
  
1.  En **administración de BizTalk Server**, seleccione **partes**. 

2. En el **entidades y perfiles empresariales** página, seleccione cualquiera de los dos perfiles de negocio que contienen el acuerdo que desea editar.  
  
3.  En el **contratos** sección, haga clic en el acuerdo y, a continuación, seleccione **habilitar** o **deshabilitar**. 
  
    > [!NOTE]
    >  Cuando se crea un acuerdo por primera vez, siempre está habilitado de forma predeterminada. El **habilitar** opción está disponible solo cuando el acuerdo está deshabilitado. El **deshabilitar** opción está disponible solo cuando el acuerdo está habilitado.  

## <a name="delete-an-agreement"></a>Eliminar un acuerdo  
1.  En **administración de BizTalk Server**, seleccione **partes**. 
  
2.  En el **entidades y perfiles empresariales** página, seleccione cualquiera de los dos perfiles de negocio que contienen el acuerdo que desea eliminar.  
  
3.  En el **contratos** sección, haga clic en el acuerdo que desea eliminar y, a continuación, seleccione **eliminar**.  
  
4.  En el **Confirmar eliminación de acuerdo** cuadro de diálogo, seleccione **Sí** para eliminar el acuerdo.  

      
## <a name="see-also"></a>Vea también  
 [Administrar soluciones EDI y AS2](../core/managing-edi-and-as2-solutions.md)