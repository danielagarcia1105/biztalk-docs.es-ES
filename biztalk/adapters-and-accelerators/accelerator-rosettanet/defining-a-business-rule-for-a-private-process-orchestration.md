---
title: Definir una regla de negocios para una orquestación de procesos privados | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, policies
- vocabularies, saving
- private processes, orchestrations
- business rules, private processes
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- policies, deploying
- vocabularies, creating
- orchestrations, private-process orchestrations
- private processes, customizing
- policies, publishing
- business rules, Set elements
- creating, policies
- customizing private processes
- Set elements
- business rules, orchestrations
- publishing, vocabularies
- vocabularies, publishing
- creating, rules
- business rules, Get elements
- policies, saving
- publishing, policies
- Get elements
- orchestrations, business rules
- rules
- private processes, business rules
- policies, creating
ms.assetid: 5d2b0257-1b15-482b-a562-798b808e9a2d
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 771ef551d70ba6e8d4aa7300ac16967638f471b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968101"
---
# <a name="defining-a-business-rule-for-a-private-process-orchestration"></a>Definir una regla de negocios para una orquestación de procesos privados
Puede definir una regla de negocios para su uso en un proceso privado de confirmación. Esto permite modificar la regla de negocios dinámicamente sin detener la orquestación de procesos de privados. Este proceso usa el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] motor de reglas de negocios. Este proceso implica los pasos siguientes:  
  
1. Agregar un nuevo vocabulario. Esto implica definir el valor constante de al menos un vocabulario. Esto establece un umbral de regla de negocios. También implica la definición de documento XML `Get` y `Set` elementos. Esto establece cómo Microsoft [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] usa el umbral.  
  
2. Agregar una nueva directiva. Esto implica la creación de una directiva, la creación de un conjunto de reglas y, a continuación, guardar, publicar e implementar la directiva.  
  
3. Una llamada a la regla de negocio desde la orquestación de procesos privado. Esto implica agregar un **reglas de llamada** forma a la orquestación.  
  
   El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye un ejemplo de [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] directiva empresarial, samplebtarnpolicy.xml, en \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\PipAutomation\3A4. Para obtener más información, consulte [directiva empresarial de BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md).  
  
   PIP3A4PrivateResponder.odx orquestación es una orquestación de procesos de privados de ejemplo que muestra cómo implementar un proceso de interfaz de socio (PIP)-incorporación de una regla de negocios de procesos privado Respondedor específico. Para obtener más información acerca de este ejemplo, vea [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).  
  
   Para obtener más información acerca de vocabularios y directivas, vea el tema "Desarrollar con las reglas de negocios" en BizTalk Server.  
  
### <a name="to-add-a-new-vocabulary"></a>Para agregar un vocabulario nuevo  
  
1. Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **compositor**.  
  
2. Si el **abierto regla Store** abre el cuadro de diálogo, seleccione el **motor de reglas de BizTalk** base de datos que configuró en el servidor actual y, a continuación, haga clic en **Aceptar**.  
  
3. En el Compositor de reglas de negocios de Microsoft, en el panel Explorador de hechos, haga clic en **vocabularios**y, a continuación, haga clic en **Agregar nuevo vocabulario**.  
  
4. En el panel de propiedades (parte inferior izquierda), establezca el **nombre** propiedad en el nombre del vocabulario adecuado y, a continuación, presione **ENTRAR**.  
  
5. Expanda la carpeta de vocabulario que acaba de crear, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva definición**.  
  
6. En la página **Asistente para definición de vocabulario** , seleccione **Valor, rango de valores o conjunto de valores constantes**y, a continuación, haga clic en **Siguiente**.  
  
7. En el **constante de valor, rango de valores o conjunto de valores** página, en el **nombre de la definición** , escriba el nombre del valor constante de vocabulario adecuado, como **máximo permitido de cantidad** y, a continuación, haga clic en **siguiente**.  
  
8. En el **definir un valor constante** página, en el **campo de valor** , escriba el umbral y, a continuación, haga clic en **finalizar**.  
  
### <a name="to-define-get-and-set-elements"></a>Para definir Get y establecer los elementos  
  
1.  En el Compositor de reglas de negocio, en el panel Explorador de hechos, en la carpeta de vocabulario creada en "para agregar un nuevo procedimiento de vocabulario", haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva definición**.  
  
2.  En el **Asistente para definición de vocabulario** página, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.  
  
3.  En el **atributo o elemento de documento XML** página, en el cuadro de texto Nombre de la definición, escriba un nombre para un **obtener** elemento.  
  
4.  Haga clic en **examinar**, desplácese a la ubicación del esquema que desea usar, seleccione el archivo de esquema y, a continuación, haga clic en **abierto**.  
  
5.  Si el **seleccionar el nodo raíz** abre la página, seleccione el nodo raíz que examinar.  
  
6.  En el **Seleccionar enlace** página, desplazarse al campo para el que desea definir el umbral y, a continuación, haga clic en **Aceptar**.  
  
7.  En el **tipo de documento** , escriba el nombre del documento.  
  
8.  En el **tipo de operación** sección, seleccione **realizar operación "Get"**.  
  
9. Haga clic en **Finalizar**.  
  
10. Repita estos pasos para definir uno o varios `Set` operaciones, seleccionadas **realizar operación "Set"** para el **tipo de operación**.  
  
### <a name="to-save-and-publish-the-vocabulary"></a>Para guardar y publicar el vocabulario  
  
1.  En el Compositor de reglas de negocio, en el panel Explorador de hechos, en la carpeta de vocabulario que ha creado, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.  
  
2.  En el panel Explorador de hechos, en la carpeta 3A4PurchaseOrderVocabulary, haga clic en **versión 1.0**y, a continuación, seleccione **publicar**.  
  
### <a name="to-add-a-new-policy-and-rules"></a>Para agregar una nueva directiva y reglas  
  
1.  En el Compositor de reglas de negocio, en el panel Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.  
  
2.  Haga clic en **Policy1**.  
  
3.  En el panel Propiedades, establezca la **nombre** propiedad en el nombre de la directiva adecuada.  
  
4.  En el panel Explorador de directivas, en la carpeta para la nueva directiva, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva regla**.  
  
5.  Haga clic en **Rule1**.  
  
6.  En el panel Propiedades, establezca la **nombre** propiedad en el nombre de regla desee y, a continuación, presione **ENTRAR**.  
  
7.  En el Compositor de reglas, en el **IF** panel, haga clic en **condiciones**y, a continuación, seleccione una condición lógica, si procede.  
  
8.  En el panel Explorador de hechos, en **vocabularios**, expanda **predicados**, expanda **versión 1.0 - publicada**, seleccione el predicado que desee, arrástrelo a la superficie del compositor de reglas y, a continuación, colóquela en **condiciones** o el operador lógico.  
  
9. En el panel Explorador de hechos, en la carpeta vocabularios, expanda el vocabulario que ha creado, **versión 1.0 - publicada**, seleccione un `Get` o `Set` elemento, arrástrelo a la superficie del compositor y colóquela en **argumento1**.  
  
10. En la carpeta de vocabulario, seleccione un `Get` o `Set` elemento, arrástrelo a la superficie del compositor y colóquela en **argumento2**.  
  
11. En la carpeta de vocabulario, seleccione un `Set` elemento, arrástrelo a la superficie del compositor y colóquela en la **acciones** cuadro en el panel entonces.  
  
12. Si una variable está asociada con el `Set` elemento, haga clic en la variable, realizar cambios según corresponda y, a continuación, presione **ENTRAR**. Si es necesario, repita Sí `Set` elementos.  
  
### <a name="to-save-publish-and-deploy-the-policy"></a>Para guardar, publicar e implementar la directiva  
  
1.  Cuando haya terminado de definir las reglas, en el Compositor de reglas de negocio, en el panel Explorador de directivas, en la carpeta de directivas que ha creado, haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.  
  
2.  En el panel Explorador de directivas, en la carpeta de directivas que ha creado, haga clic en **versión 1.0**y, a continuación, haga clic en **publicar**.  
  
3.  En el panel Explorador de directivas, en la carpeta de directivas que ha creado, haga clic en **versión 1.0**y, a continuación, haga clic en **implementar**.  
  
### <a name="to-call-the-business-rule-from-the-orchestration"></a>Para llamar a la regla de negocio desde la orquestación  
  
1.  Inicie **Microsoft Visual Studio 2012**.  
  
2.  En el **archivo** menú, elija Abrir y, a continuación, haga clic en **proyecto/solución**.  
  
3.  Busque la solución que contiene la orquestación que se debe llamar a la regla de negocios de y, a continuación, haga clic en **abierto**.  
  
4.  Haga clic en **vista**, apunte a **Other Windows**y, a continuación, haga clic en **Vista orquestación**.  
  
5.  Expanda **Variables**. Asegúrese de que la lista de variables de orquestación contiene una variable que corresponda a cada parámetro de la directiva empresarial que se llame desde la orquestación. Asegúrese de que la variable tiene el mismo tipo que el parámetro de directiva. Si la lista no contiene una variable de orquestación para cada parámetro de directiva, haga clic en **Variables**y, a continuación, haga clic en **nueva Variable**. En Vista orquestación, escriba un nombre de variable y, a continuación, en la ventana Propiedades, escriba el tipo del parámetro.  
  
6.  Desde el **cuadro de herramientas**, arrastre un **reglas de llamada** dar forma a la superficie de diseño de orquestación y, a continuación, colóquelo bajo el **recepción** forma.  
  
7.  Haga doble clic en el **reglas de llamada** forma.  
  
8.  En el **seleccione la directiva empresarial desea llamar** , seleccione la directiva empresarial en la lista desplegable.  
  
9. Para el primer parámetro que se muestra, para **nombre del parámetro**, seleccione un nombre de la lista desplegable.  
  
    > [!NOTE]
    >  BTARN rellena el **parámetro de directiva** lista con todos los parámetros de la directiva empresarial. Para cada parámetro en la lista, BTARN entra en un valor en **tipo de parámetro** desde la directiva empresarial. En la lista desplegable asociada **nombre del parámetro**, BTARN entra en los nombres de todas las variables de la lista de variables de la orquestación que tenga el mismo tipo que los parámetros de directiva. Al seleccionar una variable de orquestación, va a asociar esa variable con el parámetro de directiva. Puede ver las variables de orquestación en Vista orquestación.  
  
10. Repita el paso 9 para todos los demás parámetros.  
  
11. En la ventana de diseño de orquestación, escriba todas las formas adicionales necesarias para el procesamiento asociado con la directiva empresarial, incluida la adición de un **decisión** forma bajo la **reglas de llamada** forma.  
  
    > [!NOTE]
    >  Para obtener un ejemplo de cómo usar un **reglas de llamada** forma en una orquestación, vea la orquestación PIP3A4PrivateResponder.odx incluida en el SDK de BTARN. Se encuentra en \< *unidad*\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para RosettaNet\SDK\PipAutomation\3A4\PR. Para obtener más información, consulte [3A4 privado Respondedor orquestación con una regla de negocios](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md).  
  
12. Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Guía de programación](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)   
 [Directiva empresarial BTARN de ejemplo](../../adapters-and-accelerators/accelerator-rosettanet/sample-btarn-business-policy.md)   
 [Orquestación del respondedor privado 3A4 mediante una regla de negocio](../../adapters-and-accelerators/accelerator-rosettanet/3a4-private-responder-orchestration-using-a-business-rule.md)