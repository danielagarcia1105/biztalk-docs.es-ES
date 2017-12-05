---
title: "Paso 6: Configurar formas de orquestación (Contoso) | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, configuring shapes
- private process tutorial, configuring orchestration shapes
ms.assetid: ce680693-cf72-4ca6-a062-019de5a9257b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9310e9b287f35876a137d13dbcc2d1fa39ba9588
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="step-6-configuring-orchestration-shapes-contoso"></a>Paso 6: Configurar formas de orquestación (Contoso)
En este paso, configurará las formas de orquestación que agregó a la orquestación PrivateResponder que creó en [paso 5: modificar la orquestación de procesos privado de Contoso](../../adapters-and-accelerators/accelerator-rosettanet/step-5-modifying-the-contoso-private-process-orchestration.md). Esto incluye la configuración de la comunicación entre [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server y el sistema de planeamiento de recursos empresariales (ERP) de Contoso.  
  
### <a name="to-configure-the-constructmessagepip3a2requestmessage-shape"></a>Para configurar la forma ConstructMessagePIP3A2RequestMessage  
  
1.  Tras seleccionar PrivateResponder.odx en el Explorador de soluciones, en la superficie de diseño de orquestación, seleccione la forma **ConstructPIP3A2RequestMessage** .  
  
2.  En la ventana Propiedades, seleccione la propiedad **Mensajes construidos** , seleccione **PIP3A2RequestMessage** de la lista desplegable y, después, presione **ENTRAR**.  
  
3.  Haga doble clic en la forma **Asignación de mensajes** dentro de la forma **ConstructPIP3A2RequestMessage** para abrir el Editor de expresiones de BizTalk.  
  
4.  En el Editor de expresiones de BizTalk, escriba lo siguiente:  
  
    ```  
    PIP3A2RequestMessage = Helper.NormalizeHeader(Microsoft.Solutions.BTARN.Shared.SCContainer.ConvertFromContainer(ActionMessage));  
    ```  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-constructcontoso3a2requestmessage-transform-shape"></a>Para configurar la forma de transformación ConstructContoso3A2RequestMessage  
  
1.  En la superficie de diseño de orquestación, haga clic en la forma **ConstructContoso3A2RequestMessage** .  
  
2.  En la ventana Propiedades, seleccione la propiedad **Mensajes construidos** y, después, seleccione **Contoso3A2RequestMessage** de la lista desplegable.  
  
3.  Seleccione la forma **Transform_1** dentro de la forma **ConstructContoso3A2RequestMessage** .  
  
4.  En la ventana Propiedades, seleccione la propiedad **Nombre de asignación** y, después, haga clic en el botón de puntos suspensivos (**…**) para abrir el cuadro de diálogo Configuración de transformación.  
  
5.  En el cuadro de diálogo Configuración de transformación, haga clic en **mapa existente**y, a continuación, en la **cuadro de nombre completo de asignación**, seleccione  **\<seleccionar del ensamblado mencionado\>**  en la lista desplegable para abrir el cuadro de diálogo Seleccionar tipo de artefacto.  
  
6.  En el cuadro de diálogo Seleccionar tipo de artefacto, seleccione el ensamblado **ContosoPriceAndAvailability** en el panel izquierdo, seleccione la asignación **PIP3A2RequestToContosoPriceRequest** en el panel derecho y, después, haga clic en **Aceptar**.  
  
7.  En el cuadro de diálogo Configuración de transformación, seleccione **Origen** en el panel izquierdo.  
  
8.  Haga clic en el cuadro vacío en **Nombre de variable**y, a continuación, seleccione **PIP3A2RequestMessage** de la lista desplegable.  
  
9. Seleccione **destino** en el panel izquierdo, haga clic en **Contoso3A2RequestMessage** desde el **VariableName** lista desplegable y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-configure-the-execute3a2vocabulary-call-rules-shape"></a>Para configurar la forma reglas de llamada Execute3A2Vocabulary  
  
1.  En la superficie de diseño de orquestación, haga doble clic en la forma **Execute3A2Vocabulary** dentro de la forma **Scope_1** .  
  
2.  En el cuadro de diálogo Configuración de directivas de reglasLlamada, seleccione **3A2PriceAvailabilityPolicy** en la lista desplegable **Seleccione la directiva empresarial a la que desea llamar** .  
  
3.  En la lista **Especificar parámetros de directivas** , haga clic en **Haga clic aquí para agregar una nueva fila**y, después, seleccione **Contoso3A2ResponseMessage** en la lista desplegable.  
  
4.  Haga clic en **Aceptar**.  
  
### <a name="to-configure-the-construct3a2responsemessage-transform-shape"></a>Para configurar la forma de transformación Construct3A2ResponseMessage  
  
1.  En la superficie de diseño de orquestación, haga clic en la forma **Construct3A2ResponseMessage** .  
  
2.  En la ventana Propiedades, seleccione la propiedad **Mensajes construidos** , después seleccione **PIP3A2ResponseMessage** en la lista desplegable y, después, presione **ENTRAR**.  
  
3.  Seleccione la forma **Transform_2** dentro de la forma **Construct3A2ResponseMessage** .  
  
4.  En la ventana Propiedades, haga clic en **Asignar nombre**y, después, haga clic en el botón de puntos suspensivos (**…**).  
  
5.  En el cuadro de diálogo Configuración de Transformación, haga clic en **Nueva asignación**.  
  
6.  En el cuadro **Asignación válida** , escriba **ContosoPriceAndAvailability.ContosoResponse3A2RequestMerge**.  
  
7.  En el cuadro de diálogo Configuración de transformación, seleccione **Origen** en el panel izquierdo.  
  
8.  Haga clic en la etiqueta **Haga clic aquí para agregar una nueva fila** dentro de **Nombre de variable**y, después, seleccione **PIP3A2RequestMessage** en la lista desplegable.  
  
9. Haga clic en la etiqueta **Haga clic aquí para agregar una nueva fila** dentro de **Nombre de variable** y, después, seleccione **Contoso3A2ResponseMessage** en la lista desplegable.  
  
10. Seleccione **Destino** en el panel izquierdo, seleccione **PIP3A2ResponseMessage** en la lista desplegable **Nombre de variable** y, después, haga clic en **Aceptar**.  
  
11. En el Explorador de soluciones, haga clic con el botón secundario en el archivo **ContosoResponse3A2RequestMerge.btm** y, después, haga clic en **Abrir con**.  
  
12. En el cuadro de diálogo **Abrir con - ContosoResponse3A2RequestMerge.btm** , seleccione **Editor XML** en la lista de programas y, después, haga clic en **Aceptar**. Haga clic en **Sí**.  
  
    > [!NOTE]
    >  Debido al elevado número de vínculos necesarios para esta asignación, este tutorial usa [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] 2008 HTML/XML, Editor para construir la asignación copiando manualmente la información del mapa.  
  
13. En el menú **Editar** , haga clic en **Seleccionar todo**.  
  
14. Copie el texto XML siguiente en el portapapeles: En el menú **Editar** , haga clic en **Pegar** para sobrescribir la asignación actual:  
  
    ```  
    <?xml version="1.0" encoding="utf-16"?>  
    <!-- Generated using BizTalk Mapper on Mon, Nov 08 2004 06:20:59 PM -->  
    <!-- Copyright (c) Microsoft Corporation.  All rights reserved. -->  
    <mapsource Name="BizTalk Map" BizTalkServerMapperTool_Version="2.0" Version="2" XRange="100" YRange="420" OmitXmlDeclaration="Yes" CopyPIs="No" method="xml" xmlVersion="1.0" IgnoreNamespacesForLinks="Yes"><SrcTree><xs:schema xmlns:tns="http://schemas.microsoft.com/BizTalk/2003/aggschema" xmlns:ns2="http://Contoso.com/Price" xmlns:ns1="http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd" xmlns:b="http://schemas.microsoft.com/BizTalk/2003" targetNamespace="http://schemas.microsoft.com/BizTalk/2003/aggschema" xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:import schemaLocation="Microsoft.Solutions.BTARN.Schemas.RNPIPs._3A2PriceAndAvailabilityQueryMessageGuideline_v1_3" namespace="http://schemas.microsoft.com/biztalk/btarn/2004/3A2PriceAndAvailabilityQueryMessageGuideline_v1_3.dtd"/>  
    <xs:import schemaLocation="ContosoPriceAndAvailability.ContosoPriceSchema" namespace="http://Contoso.com/Price"/>  
    <xs:element name="Root">  
    <xs:complexType>  
    <xs:sequence>  
    <xs:element name="InputMessagePart_0">  
    <xs:complexType>  
    <xs:sequence>  
    <xs:element ref="ns1:Pip3A2PriceAndAvailabilityQuery"/>  
    </xs:sequence>  
    </xs:complexType>  
    </xs:element>  
    <xs:element name="InputMessagePart_1">  
    <xs:complexType>  
    <xs:sequence>  
    <xs:element ref="ns2:rootPriceResponse"/>  
    </xs:sequence>  
    </xs:complexType>  
    </xs:element>  
    </xs:sequence>  
    </xs:complexType>  
    </xs:element>  
    </xs:schema></SrcTree><TrgTree RootNode_Name="Pip3A2PriceAndAvailabilityResponse"><Reference Location="Microsoft.Solutions.BTARN.Schemas.RNPIPs._3A2PriceAndAvailabilityResponseMessageGuideline_v1_3"/></TrgTree><ScriptTypePrecedence><CSharp Enabled="Yes"/><ExternalAssembly Enabled="Yes"/><VbNet Enabled="Yes"/><JScript Enabled="Yes"/><XsltCallTemplate Enabled="Yes"/><Xslt Enabled="Yes"/></ScriptTypePrecedence><TreeValues><TestValues/><ConstantValues/></TreeValues><Pages><Page Name="Page 1"><Links><Link LinkID="1" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='GlobalProductStatusCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='GlobalProductStatusCode']" Label=""/><Link LinkID="2" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='unitPrice']/*[local-name()='FinancialAmount']/*[local-name()='GlobalCurrencyCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='unitPrice']/*[local-name()='FinancialAmount']/*[local-name()='GlobalCurrencyCode']" Label=""/><Link LinkID="3" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='GlobalProductIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='GlobalProductIdentifier']" Label=""/><Link LinkID="4" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='GlobalPartnerClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='GlobalPartnerClassificationCode']" Label=""/><Link LinkID="5" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='ProprietaryProductIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='ProductIdentification']/*[local-name()='PartnerProductIdentification']/*[local-name()='ProprietaryProductIdentifier']" Label=""/><Link LinkID="6" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='LineNumber']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='LineNumber']" Label=""/><Link LinkID="7" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='GlobalPricingTypeCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='GlobalPricingTypeCode']" Label=""/><Link LinkID="8" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='thisDocumentIdentifier']/*[local-name()='ProprietaryDocumentIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='requestingDocumentIdentifier']/*[local-name()='ProprietaryDocumentIdentifier']" Label=""/><Link LinkID="9" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='thisDocumentGenerationDateTime']/*[local-name()='DateTimeStamp']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='requestingDocumentDateTime']/*[local-name()='DateTimeStamp']" Label=""/><Link LinkID="10" LinkFrom="1" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='thisDocumentIdentifier']/*[local-name()='ProprietaryDocumentIdentifier']" Label=""/><Link LinkID="11" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalLocationIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalLocationIdentifier']" Label=""/><Link LinkID="12" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='cityName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='cityName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="13" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine1']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine1']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="14" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine2']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine2']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="15" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine3']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='addressLine3']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="16" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalCountryCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='GlobalCountryCode']" Label=""/><Link LinkID="17" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='NationalPostalCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='NationalPostalCode']" Label=""/><Link LinkID="18" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailabilityQuery']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='regionName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseAddress']/*[local-name()='PhysicalAddress']/*[local-name()='regionName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="19" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" Label=""/><Link LinkID="20" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" Label=""/><Link LinkID="21" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" Label=""/><Link LinkID="22" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" Label=""/><Link LinkID="23" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="24" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" Label=""/><Link LinkID="25" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" Label=""/><Link LinkID="26" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='GlobalPartnerRoleClassificationCode']" Label=""/><Link LinkID="27" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='GlobalPartnerClassificationCode']" Label=""/><Link LinkID="28" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalBusinessIdentifier']" Label=""/><Link LinkID="29" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='PartnerDescription']/*[local-name()='BusinessDescription']/*[local-name()='GlobalSupplyChainCode']" Label=""/><Link LinkID="30" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='contactName']/*[local-name()='FreeFormText']" Label=""/><Link LinkID="31" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='telephoneNumber']/*[local-name()='CommunicationsNumber']" Label=""/><Link LinkID="32" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_0']/*[local-name()='Pip3A2PriceAndAvailabilityQuery']/*[local-name()='toRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='fromRole']/*[local-name()='PartnerRoleDescription']/*[local-name()='ContactInformation']/*[local-name()='EmailAddress']" Label=""/><Link LinkID="33" LinkFrom="2" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='thisDocumentGenerationDateTime']/*[local-name()='DateTimeStamp']" Label=""/><Link LinkID="34" LinkFrom="3" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='GlobalDocumentFunctionCode']" Label=""/><Link LinkID="35" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_1']/*[local-name()='rootPriceResponse']/*[local-name()='Products']/@*[local-name()='Price']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='productUnit']/*[local-name()='ProductPackageDescription']/*[local-name()='unitPrice']/*[local-name()='FinancialAmount']/*[local-name()='MonetaryAmount']" Label=""/><Link LinkID="36" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_1']/*[local-name()='rootPriceResponse']/*[local-name()='Products']/@*[local-name()='NumberAvailable']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='ProductLineItem']/*[local-name()='ProductQuantity']" Label=""/><Link LinkID="37" LinkFrom="/*[local-name()='<Schema>']/*[local-name()='Root']/*[local-name()='InputMessagePart_1']/*[local-name()='rootPriceResponse']/*[local-name()='Products']/@*[local-name()='NumberAvailable']" LinkTo="/*[local-name()='<Schema>']/*[local-name()='Pip3A2PriceAndAvailabilityResponse']/*[local-name()='ProductPriceAndAvailability']/*[local-name()='WarehouseInformationResource']/*[local-name()='warehouseQuantity']/*[local-name()='ProductQuantity']" Label=""/></Links><Functoids><Functoid FunctoidID="1" X-Cell="52" Y-Cell="231" Functoid-FID="260" Functoid-Name="Scripting" Label=""><Input-Parameters/><ScripterCode><Script Language="CSharp"><![CDATA[///*Uncomment the following code for a sample Inline C# function  
    //that concatenates two inputs. Change the number of parameters of  
    //this function to be equal to the number of inputs connected to this functoid.*/  
  
    public string returnGUID()  
    {  
    return System.Guid.NewGuid().ToString();  
    }]]></Script></ScripterCode></Functoid><Functoid FunctoidID="2" X-Cell="55" Y-Cell="236" Functoid-FID="260" Functoid-Name="Scripting" Label=""><Input-Parameters/><ScripterCode><Script Language="CSharp"><![CDATA[public string GetRNDateTime()  
    {  
    DateTime dt;  
    dt=DateTime.UtcNow;  
    string dateVal = dt.ToString("u");  
    dateVal = dateVal.Replace("-","");  
    dateVal = dateVal.Replace(":","");  
    dateVal  =dateVal.Replace(" ","T");  
    string sec = "."+ DateTime.UtcNow.Millisecond.ToString()+"Z";  
    dateVal  =dateVal.Replace("Z",sec);  
    return  dateVal;  
    }]]></Script></ScripterCode></Functoid><Functoid FunctoidID="3" X-Cell="54" Y-Cell="239" Functoid-FID="107" Functoid-Name="String Concatenate" Label=""><Input-Parameters><Parameter Type="Constant" Value="Response" Guid="{FA85B113-6FB4-4932-A125-5CF751A536B5}"/></Input-Parameters></Functoid></Functoids></Page></Pages></mapsource>  
    ```  
  
15. En el menú **Archivo** , haga clic en **Guardar todo**.  
  
### <a name="to-configure-the-expression1-shape"></a>Para configurar la forma de Expression_1  
  
1.  En el Explorador de soluciones, haga doble clic en **PrivateResponder.odx**.  
  
2.  En la superficie de diseño de orquestación, haga doble clic en la forma **Expression_1** para abrir el Editor de expresiones de BizTalk.  
  
3.  En el Editor de expresiones de BizTalk, escriba el código siguiente:  
  
    ```  
    contosoResponseXML = PIP3A2ResponseMessage;  
  
    submitMessage.SubmitMessage(  
      Microsoft.Solutions.BTARN.Shared.MessageCategory.AsyncResponse,  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCDestinationPartnerID),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCSourcePartnerID),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPCode),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCInstanceID),  
    ActionMessage(Microsoft.Solutions.BTARN.GlobalSchemas.SCPIPVersion),   
    Helper.ReturnSCWithDocType(contosoResponseXML) );  
    ```  
  
4.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Paso 7: Creación y configuración de puertos](../../adapters-and-accelerators/accelerator-rosettanet/step-7-creating-and-configuring-ports.md)