FROM ft-rails:on-build
EXPOSE 3000
CMD ["rails", "s", "-b", "0.0.0.0", "-p", "3000"]

# Use app this app to test - https://bitbucket.org/railstutorial/sample_app_4th_ed/overview
# https://runnable.com/docker/rails/dockerize-your-ruby-on-rails-application
# Before build check versions in Gemfile.lock
# Check
# at rails dir : docker build -t ft-rails:on-build . 
# docker build -t image02 .
# docker run -it --rm -p 3000:3000 image02
# visit http://192.168.99.100:3000 