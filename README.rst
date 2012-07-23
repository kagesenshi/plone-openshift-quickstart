=====================
Plone on OpenShift!
=====================

Plone is a free and open source content management system built on top of the
Zope application server. In principle, Plone can be used for any kind of
website, including blogs, internet sites, webshops and internal websites. It
is also well positioned to be used as a document publishing system and
groupware collaboration tool. The strengths of Plone are its flexible and
adaptable workflow, very good security, extensibility, high usability and
flexibility.

Running on OpenShift
=====================

Create an account at http://openshift.redhat.com/

Create a DIY application::
  
  rhc app create -a plone -t diy-0.1

Add this upstream Plone repo::
  
  cd plone
  git remote add upstream -m master git@github.com/kagesenshi/plone-openshift-quickstart
  git pull -s recursive -X theirs upstream master

Then push the repo upstream (this will take quite a while to finish)::
  
  git push

Thats it, you now can check out your application at::

  http://plone-$yournamespace.rhcloud.com

Notes
======

Default login
--------------

Default admin login is ``admin:OpenShiftAdmin``. Remember to change it 
here: ``http://plone-$yournamespace.rhcloud.com/acl_users/manage_users``.

Virtual hosting
---------------

You may have multiple Plone sites per deployment and you may assign a domain
to each of the sites. To setup virtual hosting for your Plone site, add an 
entry here:
``http://plone-$yournamespace.rhcloud.com/virtual_hosting/manage_edit``


