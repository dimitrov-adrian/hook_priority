CONTENTS OF THIS FILE
---------------------

 * Introduction
 * Features
 * Examples
 * Requirements
 * Downloads
 * Installation
 * Contacts


INTRODUCTION
------------

Allow prioritization of the Drupal's hooks. Set weight for each hook in Drupal
is not so trivial as in other CMSs so, this plugin attempt to fix this.


FEATURES
--------
 * Set weight for hook
 * Set auto weight for hook, calculated by other module
 * Set hook be to beginning or ending in the stack
 

EXAMPLES
--------

Hooks are performed by a weight in ascending order.
Set function can be called without be in hook.

/*
 * Implements hook_init().
 */
function mymodule_init() {
  // do something.
}

// Set hook be performed in order where default weight is 0
hook_priority_set('mymodule_init', 100);


/*
 * Implements hook_domain_delete().
 */
function mymodule_domain_delete() {
  // do something.
}

// Set hook to be performed after the hook from module 'domain_conf'
hook_priority_set_after('mymodule_domain_delete', 'domain_conf');


Overview:

// Set pririty/weight for a hook to specific number.
hook_priority_set(string <hookname>, int <weight>);

// Move hook to be performed as first.
hook_priority_set_first(string <hookname>);

// Move hook to be performed as last.
hook_priority_set_last(string <hookname>);

// Move hook to be performed before hook from other module.
hook_priority_set_before(string <hookname>, string <module>);

// Move hook to be performed after hook from other module.
hook_priority_set_after(string <hookname>, string <module>);


REQUIREMENTS
------------

 * Drupal 7.x


DOWNLOAD
-----------

Project page: http://drupal.org/node/1586688
Git (drupal.org): http://git.drupal.org/sandbox/dimitrov.adrian/1586688.git
Git (github): https://github.com/dimitrov-adrian/hook_priority


INSTALLATION
------------

 1) Unarchive the zip and put directory into your sites/all/modules
 2) Enable it from your admin panel -> Modules


CONTACTS
--------
Developer: Adrian Dimtrov <adimitrov@propeople.dk>
Company: ProPeople (www.wearepropeople.com)
