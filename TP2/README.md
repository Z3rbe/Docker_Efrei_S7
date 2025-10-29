#TP2
## 2.1
	You can easily start and stop real services (like databases or message queues) during tests.
	It helps you test your app with real dependencies, not just mock services.
	After the test, the containers are automatically removed.
## 2.2
	Protect sensitive info (like passwords or API keys).
	Prevent leaks of private data.
	Meet security requirements.
	Control who can access the sensitive data.
## 2.3
	We put needs: build-and-test-backend to make sure this job runs only after the backend build and test job is done.
	If we remove it:
	The job might start too early, before the backend is ready, causing errors.
	In short, needs makes sure jobs happen in the right order.
## 2.4
	Share them with others.
	Backup the image online.
	Deploy it to different environments.
	Track versions for updates or rollbacks.
