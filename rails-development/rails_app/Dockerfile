FROM ruby:2.5.0
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN mkdir /rails_app
WORKDIR /rails_app
COPY Gemfile /rails_app/Gemfile
COPY Gemfile.lock /rails_app/Gemfile.lock
RUN bundle install && bundle update
COPY . /rails_app