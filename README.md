#Yii2 Remote Modal
by cenotia

This extension enables the use of several types of in a simplify way and using ajax.

In order to add it to your project you have to download the archive or use the composer tool which is the preferred way.

In your composer.json file add the following line

``"cenotia/yii2-remote-modal":"*"``

and run `composer update`

###In Controller

in your controller's actions (that you want to display in a modal), add the following code :

``
public function actionTest() 
{
	$request = \Yii::$app->request;
	\Yii::$app->response->format = Response::FORMAT_JSON;
	return [
		'title'=> "Test Titre",
		'content'=>"Test content", // for example: $this->renderAjax('view', [
				                   //     'model' => $model,
				                   //  ]),
		'footer'=> Html::button('Close',['class'=>'btn btn-default pull-left','data-dismiss'=>"modal"]).
		Html::button('Save',['class'=>'btn btn-primary','type'=>"submit"])
];
}

``

### In your view

The calling link would be

``<a href="/site/test" role="XXXXXXXXXID">Test</a>``

At the end of the view file, add this :

``	<?php RemoteModal::begin([
				"id"=>"XXXXXXXXXID",
				"options"=> [ "class"=>"fade slide-right "],
				"footer"=>"", // always need it for jquery plugin
				])?>
		<?php RemoteModal::end(); ?>
``

The available classes in options are :

* slide-right
* stick-up
* fill-in
* slide-up



##release trail

version 1.0.0
=============
Initial release 2016-11-1


