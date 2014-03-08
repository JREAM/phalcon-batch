Phalcon Batch
=============

This is a simple addition to allow batch MySQL INSERT, and MySQL IGNORE INSERT.

## Install
I prefer to use a BaseController whereby all my controllers extend. I also do this
with a BaseModel, but I would suggest placing this in the BaseController.

    <?php
    // BaseController.php
    class BaseController extends \Phalcon\Mvc\Controller
    {


    <?php
    TestController.php
    class TestController extends \BaseController
    {

Inside **BaseController.php** append or include the **Batch.php** content.
Then use the Batch in any controller.


        <?php
        $batch = new Batch('user_notification');
        $batch->setRows(['user_id', 'notification_id'])
                ->setValues([
                    [23,1],
                    [24,1],
                    [25,1],
                    [26,1],
                    [27,1],
                    [28,1],
                    [29,1],
                    [30,1],
            ])->insert();

This could also be a user component if you wanted.